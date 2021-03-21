---
title: ディレクトリ同期のために非ルーティング ドメインの準備を整える
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365E_SetupDirSyncLocalDir
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: e7968303-c234-46c4-b8b0-b5c93c6d57a7
description: Microsoft 365 テナントと同期する前に、展開できないドメインがオンプレミスのユーザー アカウントに関連付けられている場合の操作について説明します。
ms.openlocfilehash: e4d0e020c5792c610d501c33e8f3d5131b7a1ff0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927398"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a><span data-ttu-id="77bb6-103">ディレクトリ同期のために非ルーティング ドメインの準備を整える</span><span class="sxs-lookup"><span data-stu-id="77bb6-103">Prepare a non-routable domain for directory synchronization</span></span>

<span data-ttu-id="77bb6-104">オンプレミス ディレクトリを Microsoft 365 と同期する場合は、Azure Active Directory (Azure Active Directory) に検証済みのドメインをAD。</span><span class="sxs-lookup"><span data-stu-id="77bb6-104">When you synchronize your on-premises directory with Microsoft 365, you have to have a verified domain in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="77bb6-105">オンプレミスの Active Directory ドメイン サービス (DS) ドメインに関連付けられているユーザー プリンシパル名 (UPN) AD同期されます。</span><span class="sxs-lookup"><span data-stu-id="77bb6-105">Only the User Principal Names (UPNs) that are associated with the on-premises Active Directory Domain Services (AD DS) domain are synchronized.</span></span> <span data-ttu-id="77bb6-106">ただし、.local など、アウトできないドメインを含む UPN (例: billa@contoso.local) は、.onmicrosoft.com ドメイン (例: billa@contoso.onmicrosoft.com) に同期されます。</span><span class="sxs-lookup"><span data-stu-id="77bb6-106">However, any UPN that contains a non-routable domain, such as ".local" (example: billa@contoso.local), will be synchronized to an .onmicrosoft.com domain (example: billa@contoso.onmicrosoft.com).</span></span> 

<span data-ttu-id="77bb6-107">現在、AD DS のユーザー アカウントに .local" ドメインを使用している場合は、Microsoft 365 ドメインと適切に同期するために、billa@contoso.com などの検証済みドメインを使用するドメインを変更してください。</span><span class="sxs-lookup"><span data-stu-id="77bb6-107">If you currently use a ".local" domain for your user accounts in AD DS, it's recommended that you change them to use a verified domain, such as billa@contoso.com, in order to properly synchronize with your Microsoft 365 domain.</span></span>
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a><span data-ttu-id="77bb6-108">オンプレミスドメインが .local の場合は、どうしますか?</span><span class="sxs-lookup"><span data-stu-id="77bb6-108">What if I only have a ".local" on-premises domain?</span></span>

<span data-ttu-id="77bb6-109">Azure AD Connect を使用して、Microsoft 365 ADの Azure ADテナントに DS を同期します。</span><span class="sxs-lookup"><span data-stu-id="77bb6-109">You use Azure AD Connect for synchronizing your AD DS to the Azure AD tenant of your Microsoft 365 tenant.</span></span> <span data-ttu-id="77bb6-110">詳細については、「オンプレミス ID と Azure ID の統合」を[参照AD。](/azure/architecture/reference-architectures/identity/azure-ad)</span><span class="sxs-lookup"><span data-stu-id="77bb6-110">For more information, see [Integrating your on-premises identities with Azure AD](/azure/architecture/reference-architectures/identity/azure-ad).</span></span>
  
<span data-ttu-id="77bb6-111">Azure AD Connect は、ユーザーの UPN とパスワードを同期し、ユーザーがオンプレミスで使用するのと同じ資格情報でサインインできます。</span><span class="sxs-lookup"><span data-stu-id="77bb6-111">Azure AD Connect synchronizes your users' UPN and password so that users can sign in with the same credentials they use on-premises.</span></span> <span data-ttu-id="77bb6-112">ただし、Azure AD Connect は、Microsoft 365 によって検証されたドメインにのみユーザーを同期します。</span><span class="sxs-lookup"><span data-stu-id="77bb6-112">However, Azure AD Connect only synchronizes users to domains that are verified by Microsoft 365.</span></span> <span data-ttu-id="77bb6-113">つまり、Microsoft 365 ID は Azure ADによって管理されるので、ドメインは Azure AD。</span><span class="sxs-lookup"><span data-stu-id="77bb6-113">This means that the domain also is verified by Azure AD because Microsoft 365 identities are managed by Azure AD.</span></span> <span data-ttu-id="77bb6-114">つまり、ドメインは有効なインターネット ドメイン (.com、.org、.net、.us など) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="77bb6-114">In other words, the domain has to be a valid Internet domain (such as, .com, .org, .net, .us).</span></span> <span data-ttu-id="77bb6-115">内部の AD DS で使用するドメインが、ラウトできないドメイン (".local"など) のみを使用している場合、Microsoft 365 テナントの検証済みドメインと一致しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="77bb6-115">If your internal AD DS only uses a non-routable domain (for example, ".local"), this can't possibly match the verified domain you have for your Microsoft 365 tenant.</span></span> <span data-ttu-id="77bb6-116">この問題を解決するには、オンプレミスのドメイン DS でプライマリ ドメインAD、または 1 つ以上の UPN サフィックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="77bb6-116">You can fix this issue by either changing your primary domain in your on-premises AD DS, or by adding one or more UPN suffixes.</span></span>
  
### <a name="change-your-primary-domain"></a><span data-ttu-id="77bb6-117">プライマリ ドメインを変更する</span><span class="sxs-lookup"><span data-stu-id="77bb6-117">Change your primary domain</span></span>

<span data-ttu-id="77bb6-118">プライマリ ドメインを Microsoft 365 で確認したドメインに変更します (たとえば、contoso.com。</span><span class="sxs-lookup"><span data-stu-id="77bb6-118">Change your primary domain to a domain you have verified in Microsoft 365, for example, contoso.com.</span></span> <span data-ttu-id="77bb6-119">その後、ドメイン contoso.local を持つすべてのユーザーが、contoso.com。</span><span class="sxs-lookup"><span data-stu-id="77bb6-119">Every user that has the domain contoso.local is then updated to contoso.com.</span></span> <span data-ttu-id="77bb6-120">ただし、これは非常に複雑なプロセスであり、より簡単なソリューションについては、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="77bb6-120">This is a very involved process, however, and an easier solution is described in the following section.</span></span>
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a><span data-ttu-id="77bb6-121">UPN サフィックスを追加してユーザーを更新する</span><span class="sxs-lookup"><span data-stu-id="77bb6-121">Add UPN suffixes and update your users to them</span></span>

<span data-ttu-id="77bb6-122">microsoft 365 で確認したドメイン (またはドメイン) に一致する新しい UPN サフィックスまたはサフィックスを AD DS に登録することで、.local の問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="77bb6-122">You can solve the ".local" problem by registering new UPN suffix or suffixes in AD DS to match the domain (or domains) you verified in Microsoft 365.</span></span> <span data-ttu-id="77bb6-123">新しいサフィックスを登録した後、ユーザー の UPN を更新して、ユーザー アカウントが新しいドメイン名に置き換 billa@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="77bb6-123">After you register the new suffix, you update the user UPNs to replace the ".local" with the new domain name, for example, so that a user account looks like billa@contoso.com.</span></span>
  
<span data-ttu-id="77bb6-124">確認済みドメインを使用するために UPN を更新した後、オンプレミスのドメイン DS を Microsoft 365 とADする準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="77bb6-124">After you have updated the UPNs to use the verified domain, you are ready to synchronize your on-premises AD DS with Microsoft 365.</span></span>
  
#### <a name="step-1-add-the-new-upn-suffix"></a><span data-ttu-id="77bb6-125">手順 1: 新しい UPN サフィックスを追加する\*\*</span><span class="sxs-lookup"><span data-stu-id="77bb6-125">Step 1: Add the new UPN suffix\*\*</span></span>
  
1. <span data-ttu-id="77bb6-126">DS ドメイン ADで、[ツール] [Active Directoryドメインと信頼] \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="77bb6-126">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Domains and Trusts**.</span></span>
    
    <span data-ttu-id="77bb6-127">**または (Windows Server 2012 を所有していない場合)**</span><span class="sxs-lookup"><span data-stu-id="77bb6-127">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="77bb6-128">**Windows キー + R** を押して **[実行]** ダイアログ開き、「Domain.msc」と入力してから **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77bb6-128">Press **Windows key + R** to open the **Run** dialog, and then type in Domain.msc, and then choose **OK**.</span></span>
    
    ![[Active Directory ドメインと信頼関係] を選択します。](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. <span data-ttu-id="77bb6-130">[Active **Directory ドメインと信頼]** ウィンドウで **、[Active Directory ドメイン** と信頼] を右クリックし、[プロパティ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="77bb6-130">In the **Active Directory Domains and Trusts** window, right-click **Active Directory Domains and Trusts**, and then choose **Properties**.</span></span>
    
    ![[Active Directory ドメインと信頼] を右クリックし、[プロパティ] を選択します。](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. <span data-ttu-id="77bb6-132">**[UPN サフィックス]** タブの **[代替の UPN サフィックス]** ボックスに、新しいサフィックスを入力して **[追加]** \> **[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77bb6-132">On the **UPN Suffixes** tab, in the **Alternative UPN Suffixes** box, type your new UPN suffix or suffixes, and then choose **Add** \> **Apply**.</span></span>
    
    ![新しい UPN サフィックスを追加します](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    <span data-ttu-id="77bb6-134">サフィックスの追加が完了したら、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77bb6-134">Choose **OK** when you're done adding suffixes.</span></span> 
    
 #### <a name="step-2-change-the-upn-suffix-for-existing-users"></a><span data-ttu-id="77bb6-135">手順 2: 既存のユーザーの UPN サフィックスを変更する</span><span class="sxs-lookup"><span data-stu-id="77bb6-135">Step 2: Change the UPN suffix for existing users</span></span>
  
1. <span data-ttu-id="77bb6-136">DS ドメイン コントローラー ADサーバー マネージャーで、[ツール]  [Active Directory ユーザーとコンピューター] \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="77bb6-136">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Users and Computers**.</span></span>
    
    <span data-ttu-id="77bb6-137">**または (Windows Server 2012 を所有していない場合)**</span><span class="sxs-lookup"><span data-stu-id="77bb6-137">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="77bb6-138">**Windows キー + R** を押して **[実行]** ダイアログ開き、「Dsa.msc」と入力してから **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77bb6-138">Press **Windows key + R** to open the **Run** dialog, and then type in Dsa.msc, and then click **OK**</span></span>
    
2. <span data-ttu-id="77bb6-139">ユーザーを選択し、右クリックして **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77bb6-139">Select a user, right-click, and then choose **Properties**.</span></span>
    
3. <span data-ttu-id="77bb6-140">**[アカウント]** タブの UPN サフィックス ドロップダウン リストで、新しい UPN サフィックスを選択してから **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="77bb6-140">On the **Account** tab, in the UPN suffix drop-down list, choose the new UPN suffix, and then choose **OK**.</span></span>
    
    ![ユーザーの新しい UPN サフィックスを追加する](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. <span data-ttu-id="77bb6-142">すべてのユーザに対して、ここまでの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="77bb6-142">Complete these steps for every user.</span></span>
    
   
### <a name="use-powershell-to-change-the-upn-suffix-for-all-of-your-users"></a><span data-ttu-id="77bb6-143">PowerShell を使用してすべてのユーザーの UPN サフィックスを変更する</span><span class="sxs-lookup"><span data-stu-id="77bb6-143">Use PowerShell to change the UPN suffix for all of your users</span></span>

<span data-ttu-id="77bb6-144">更新するユーザー アカウントが多い場合は、PowerShell を使用する方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="77bb6-144">If you have a lot of user accounts to update, it's easier to use PowerShell.</span></span> <span data-ttu-id="77bb6-145">次の例では [、Get-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617241(v=technet.10)) と [Set-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617215(v=technet.10)) コマンドレットを使用して、すべての contoso.local サフィックスを DS 内の contoso.com にADします。</span><span class="sxs-lookup"><span data-stu-id="77bb6-145">The following example uses the cmdlets [Get-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617241(v=technet.10)) and [Set-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617215(v=technet.10)) to change all contoso.local suffixes to contoso.com in AD DS.</span></span> 

<span data-ttu-id="77bb6-146">たとえば、次の PowerShell コマンドを実行して、すべての contoso.local サフィックスを次のコマンドに更新 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="77bb6-146">For example, you could run the following PowerShell commands to update all contoso.local suffixes to contoso.com:</span></span>
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

<span data-ttu-id="77bb6-147">[詳細については、「Active Directory Windows PowerShell モジュール」](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617195(v=technet.10))を参照して、DS でのWindows PowerShellをADしてください。</span><span class="sxs-lookup"><span data-stu-id="77bb6-147">See [Active Directory Windows PowerShell module](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617195(v=technet.10)) to learn more about using Windows PowerShell in AD DS.</span></span>