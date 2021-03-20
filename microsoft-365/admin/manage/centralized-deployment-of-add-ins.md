---
title: 組織でアドインの集中展開が機能するかどうかを判断する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: テナントとユーザーが要件を満たしているか確認し、集中展開を使用してアドインをOfficeできます。
ms.openlocfilehash: c9f2879e989085042758cc1c5385bea45427e7ff
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915460"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="355fb-103">組織でアドインの集中展開が機能するかどうかを判断する</span><span class="sxs-lookup"><span data-stu-id="355fb-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="355fb-104">集中展開は、ほとんどのお客様が組織内のユーザーやグループに Officeアドインを展開するための、推奨される機能豊富な方法です。</span><span class="sxs-lookup"><span data-stu-id="355fb-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your organization.</span></span> <span data-ttu-id="355fb-105">管理者の場合は、このガイダンスを使用して、組織とユーザーが要件を満たしていることを確認し、集中展開を使用できます。</span><span class="sxs-lookup"><span data-stu-id="355fb-105">If you're an admin, use this guidance to determine if your organization and users meet the requirements so that you can use Centralized Deployment.</span></span>

<span data-ttu-id="355fb-106">一元展開には、次のような利点があります。</span><span class="sxs-lookup"><span data-stu-id="355fb-106">Centralized Deployment provides the following benefits:</span></span>
  
- <span data-ttu-id="355fb-107">グローバル管理者は、アドインをユーザーに直接割り当て、グループ経由で複数のユーザーに割り当て、組織内のすべてのユーザーに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="355fb-107">A Global admin can assign an add-in directly to a user, to multiple users via a group, or to everyone in the organization.</span></span>
    
- <span data-ttu-id="355fb-108">関連するアプリケーションOfficeすると、アドインが自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="355fb-108">When the relevant Office application starts, the add-in automatically downloads.</span></span> <span data-ttu-id="355fb-109">アドインがアドイン コマンドをサポートしている場合、アドインは自動的にアドイン アプリケーション内のリボンにOfficeされます。</span><span class="sxs-lookup"><span data-stu-id="355fb-109">If the add-in supports add-in commands, the add-in automatically appears in the ribbon within the Office application.</span></span>
    
- <span data-ttu-id="355fb-110">管理者がアドインをオフまたは削除した場合、またはユーザーが Azure Active Directory またはアドインが割り当てられているグループから削除された場合、ユーザーのアドインは表示されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="355fb-110">Add-ins no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span>

<span data-ttu-id="355fb-111">集中展開では、Windows、Mac、および Online の 3 つのデスクトップ プラットフォームがサポートOfficeされます。</span><span class="sxs-lookup"><span data-stu-id="355fb-111">Centralized Deployment supports three desktop platforms Windows, Mac and Online Office apps.</span></span> <span data-ttu-id="355fb-112">集中展開では、iOS と Android (Outlook Mobile アドインのみ) もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="355fb-112">Centralized Deployment also supports iOS and Android (Outlook Mobile Add-ins Only).</span></span>

<span data-ttu-id="355fb-113">すべてのユーザーのクライアントにアドインが表示されるには、最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="355fb-113">It can take up to 24 hours for an add-in to show up for client for all users.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="355fb-114">Requirements</span><span class="sxs-lookup"><span data-stu-id="355fb-114">Requirements</span></span>

<span data-ttu-id="355fb-115">アドインの一元展開では、ユーザーが Microsoft 365 Enterprise SKU E3/E5/F3 または Business SKU: Business Basic、Business Standard、Business Premium (および組織 ID を使用して Office にサインイン) を使用し、Exchange Online およびアクティブな Exchange Online メールボックスを使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="355fb-115">Centralized deployment of add-ins requires that the users are using Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium (and are signed into Office using their organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="355fb-116">サブスクリプション ディレクトリが Azure Active Directory に存在するか、Azure Active Directory にフェデレーションされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="355fb-116">Your subscription directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="355fb-117">以下に示すアプリケーションと Exchange に関するOffice要件を確認したり、集中展開互換性チェッカー [を使用することができます](#centralized-deployment-compatibility-checker)。</span><span class="sxs-lookup"><span data-stu-id="355fb-117">You can view specific requirements for Office and Exchange below, or use the [Centralized Deployment Compatibility Checker](#centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="355fb-118">一元展開は、次の機能をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="355fb-118">Centralized Deployment doesn't support the following:</span></span>
  
- <span data-ttu-id="355fb-119">Office 2013 の Word、Excel、または PowerPoint を対象とするアドイン</span><span class="sxs-lookup"><span data-stu-id="355fb-119">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span> 
- <span data-ttu-id="355fb-120">オンプレミスのディレクトリ サービス</span><span class="sxs-lookup"><span data-stu-id="355fb-120">An on-premises directory service</span></span>
- <span data-ttu-id="355fb-121">Exchange On-Prem メールボックスへのアドインの展開</span><span class="sxs-lookup"><span data-stu-id="355fb-121">Add-in Deployment to an Exchange On-Prem Mailbox</span></span>
- <span data-ttu-id="355fb-122">SharePoint に展開するアドイン</span><span class="sxs-lookup"><span data-stu-id="355fb-122">Add-in deployment to SharePoint</span></span>  
- <span data-ttu-id="355fb-123">Teams アプリ</span><span class="sxs-lookup"><span data-stu-id="355fb-123">Teams apps</span></span>
- <span data-ttu-id="355fb-124">コンポーネント オブジェクト モデル (COM) または Visual Studio (VSTO) アドインOfficeツールの展開。</span><span class="sxs-lookup"><span data-stu-id="355fb-124">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins.</span></span>
- <span data-ttu-id="355fb-125">Sku などの Exchange Online を含む Microsoft 365 の展開: Microsoft 365 Apps for Business および Microsoft 365 Apps for Enterprise。</span><span class="sxs-lookup"><span data-stu-id="355fb-125">Deployments of Microsoft 365 that do not include Exchange Online such as SKUs: Microsoft 365 Apps for Business and Microsoft 365 Apps for Enterprise.</span></span>

### <a name="office-requirements"></a><span data-ttu-id="355fb-126">Office要件</span><span class="sxs-lookup"><span data-stu-id="355fb-126">Office Requirements</span></span>

- <span data-ttu-id="355fb-127">Word、Excel、および PowerPoint アドインの場合、ユーザーは次のいずれかを使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="355fb-127">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="355fb-128">Windows デバイスのバージョン 1704 以降の Microsoft 365 Enterprise SKU: E3/E5/F3 または Business SKU: Business Basic、Business Standard、Business Premium。</span><span class="sxs-lookup"><span data-stu-id="355fb-128">On a Windows device, Version 1704 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="355fb-129">Mac のバージョン 15.34 以降。</span><span class="sxs-lookup"><span data-stu-id="355fb-129">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="355fb-130">Outlook の場合、ユーザーは次のいずれかを使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="355fb-130">For Outlook, your users must be using one of the following:</span></span> 
  - <span data-ttu-id="355fb-131">Microsoft 365 Enterprise SKU のバージョン 1701 以降: E3/E5/F3 または Business SKU: Business Basic、Business Standard、Business Premium。</span><span class="sxs-lookup"><span data-stu-id="355fb-131">Version 1701 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="355fb-132">バージョン 1808 以降の Office Professional Plus 2019 または Office 2019。</span><span class="sxs-lookup"><span data-stu-id="355fb-132">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="355fb-133">Office Professional Plus 2016 (MSI) または Office Standard 2016 (MSI) のバージョン 16.0.4494.1000 以降\*</span><span class="sxs-lookup"><span data-stu-id="355fb-133">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="355fb-134">バージョン 15.0.4937.1000 以降の Office Professional Plus 2013 (MSI) または Office Standard 2013 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="355fb-134">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="355fb-135">バージョン 16.0.9318.1000 以降のバージョン Office 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="355fb-135">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span> 
- <span data-ttu-id="355fb-136">iOS 用 Outlook モバイルのバージョン 2.75.0 以降</span><span class="sxs-lookup"><span data-stu-id="355fb-136">Version 2.75.0 or later of Outlook mobile for iOS</span></span> 
- <span data-ttu-id="355fb-137">Android 用 Outlook モバイルのバージョン 2.2.145 以降</span><span class="sxs-lookup"><span data-stu-id="355fb-137">Version 2.2.145 or later of Outlook mobile for Android</span></span> 
    
    <span data-ttu-id="355fb-138">\*MSI バージョンの Outlook では、"My アドイン" セクションではなく、適切な Outlook リボンに管理者がインストールしたアドインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="355fb-138">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>

### <a name="exchange-online-requirements"></a><span data-ttu-id="355fb-139">Exchange Online の要件</span><span class="sxs-lookup"><span data-stu-id="355fb-139">Exchange Online requirements</span></span>

<span data-ttu-id="355fb-140">Microsoft Exchange は、アドイン マニフェストを組織のテナント内に格納します。</span><span class="sxs-lookup"><span data-stu-id="355fb-140">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="355fb-141">アドインを展開する管理者と、それらのアドインを受け取るユーザーは、OAuth 認証をサポートするバージョンの Exchange Online 上にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="355fb-141">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>
  
<span data-ttu-id="355fb-p106">組織の Exchange 管理者に、どの構成を使用できるのかを確認してください。ユーザーごとの OAuth 認証接続は、[Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity) PowerShell コマンドレットを使用して、検証できます。</span><span class="sxs-lookup"><span data-stu-id="355fb-p106">Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity) PowerShell cmdlet.</span></span> 


### <a name="centralized-deployment-compatibility-checker"></a><span data-ttu-id="355fb-144">集中展開の互換性チェック</span><span class="sxs-lookup"><span data-stu-id="355fb-144">Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="355fb-145">集中展開互換性チェッカーを使用すると、テナントのユーザーが Word、Excel、PowerPoint 用の集中展開を使用するために設定されているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="355fb-145">Using the Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint.</span></span> <span data-ttu-id="355fb-146">Outlook のサポートでは、互換性チェックは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="355fb-146">The Compatibility Checker is not required for Outlook support.</span></span> <span data-ttu-id="355fb-147">互換性チェックをここからダウンロード [します](https://aka.ms/officeaddindeploymentorgcompatibilitychecker)。</span><span class="sxs-lookup"><span data-stu-id="355fb-147">Download the compatibility checker [here](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>
  
#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="355fb-148">互換性チェックを実行する</span><span class="sxs-lookup"><span data-stu-id="355fb-148">Run the compatibility checker</span></span>
  
1. <span data-ttu-id="355fb-149">管理者特権のウィンドウPowerShell.exeします。</span><span class="sxs-lookup"><span data-stu-id="355fb-149">Start an elevated PowerShell.exe window.</span></span>
    
2. <span data-ttu-id="355fb-150">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="355fb-150">Run the following command:</span></span>

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. <span data-ttu-id="355fb-151">**Invoke-CompatabilityCheck コマンドを実行** します。</span><span class="sxs-lookup"><span data-stu-id="355fb-151">Run the **Invoke-CompatabilityCheck** command:</span></span>

   ```powershell
   Invoke-CompatibilityCheck
   ```
   <span data-ttu-id="355fb-152">このコマンドは *_、TenantDomain_* *(TailspinToysIncorporated.onmicrosoft など) の入力を求めるプロンプトを表示します。 </span>com)\*\*_および TenantAdmin_* 資格情報 (グローバル管理者資格情報を使用)、同意を要求します。</span><span class="sxs-lookup"><span data-stu-id="355fb-152">This command prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="355fb-153">テナントのユーザー数によって、チェックが完了するのに数分または数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="355fb-153">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span> 
  
<span data-ttu-id="355fb-154">ツールの実行が完了すると、コンマ区切り (.csv) 形式で出力ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="355fb-154">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="355fb-155">ファイルは既定で **C:\windows\system32 に** 保存されます。</span><span class="sxs-lookup"><span data-stu-id="355fb-155">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="355fb-156">出力ファイルには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="355fb-156">The output file contains the following information:</span></span>
  
- <span data-ttu-id="355fb-157">ユーザー名</span><span class="sxs-lookup"><span data-stu-id="355fb-157">User Name</span></span>
    
- <span data-ttu-id="355fb-158">ユーザー ID (ユーザーのメール アドレス)</span><span class="sxs-lookup"><span data-stu-id="355fb-158">User ID (User's email address)</span></span>
    
- <span data-ttu-id="355fb-159">一元展開の準備完了 - 残りの項目が TRUE の場合</span><span class="sxs-lookup"><span data-stu-id="355fb-159">Centralized Deployment ready - If the remaining items are true</span></span>
    
- <span data-ttu-id="355fb-160">Office計画 - ライセンスOfficeのプラン</span><span class="sxs-lookup"><span data-stu-id="355fb-160">Office plan - The plan of Office they are licensed for</span></span>
    
- <span data-ttu-id="355fb-161">ライセンス認証された Office - Office をライセンス認証している場合</span><span class="sxs-lookup"><span data-stu-id="355fb-161">Office Activated - If they have activated Office</span></span>
    
- <span data-ttu-id="355fb-162">サポートされているメールボックス - OAuth 対応メールボックスを使用している場合</span><span class="sxs-lookup"><span data-stu-id="355fb-162">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>

> [!NOTE]
> <span data-ttu-id="355fb-163">サーバーの全体展開 PowerShell モジュールを使用する場合、多要素認証はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="355fb-163">Multifactor authentication is not supported when using the Central Deployment PowerShell module.</span></span>
  
## <a name="user-and-group-assignments"></a><span data-ttu-id="355fb-164">ユーザーとグループの割り当て</span><span class="sxs-lookup"><span data-stu-id="355fb-164">User and group assignments</span></span>

<span data-ttu-id="355fb-165">集中展開機能は現在、Microsoft 365 グループ、配布リスト、セキュリティ グループなど、Azure Active Directory でサポートされているグループの大部分をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="355fb-165">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Microsoft 365 groups, distribution lists, and security groups.</span></span>
  
> [!NOTE]
> <span data-ttu-id="355fb-166">メールが有効ではないセキュリティ グループは、現段階ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="355fb-166">Non-mail enabled security groups are not currently supported.</span></span> 
  
<span data-ttu-id="355fb-167">集中展開は、テナント内の個々のユーザー、グループ、およびすべてのユーザーへの割り当てをサポートします。</span><span class="sxs-lookup"><span data-stu-id="355fb-167">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="355fb-168">集中展開は、上位レベルのグループまたは親グループのないグループのユーザーをサポートしますが、ネストされたグループまたは親グループを持つグループのユーザーはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="355fb-168">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>
   
<span data-ttu-id="355fb-p110">次の例では、Sandra、Sheila、「営業部門」のグループがアドインに割り当てられています。「西海岸営業部門」は入れ子のグループのため、Bert と Fred はアドインに割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="355fb-p110">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>
  
![営業部門の図](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="355fb-172">グループにネストされたグループが含まれているかどうかを調べる</span><span class="sxs-lookup"><span data-stu-id="355fb-172">Find out if a group contains nested groups</span></span>

<span data-ttu-id="355fb-173">グループにネストされたグループが含まれているかどうかを調べる最も簡単な方法は、Outlook 内のグループの連絡先カードを確認することです。</span><span class="sxs-lookup"><span data-stu-id="355fb-173">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="355fb-174">電子メールの **[To]** フィールドにグループ名を入力し、解決時にグループ名を選択すると、グループ名にユーザーまたは入れ子になったグループが含まれているかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="355fb-174">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="355fb-175">次の例では、「テスト グループ」での Outlook 情報先カードの [ **メンバー**] タブには、ユーザーはなく、2 つのサブ グループのみが表示されています。</span><span class="sxs-lookup"><span data-stu-id="355fb-175">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 
  
![Outlook 連絡先カードの [メンバー] タブ](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
<span data-ttu-id="355fb-p112">反対のクエリを実行できます。グループを解決して、任意のグループのユーザーがいないかどうかを表示します。次の例では、「サブ グループ 1」が「テスト グループ」のメンバーである Outlook 情報先カードの [ **メンバーシップ**] タブの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="355fb-p112">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 
  
![Outlook 連絡先カードの [メンバーシップ] タブ](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
<span data-ttu-id="355fb-p113">または、Azure Active Directory Graph API でクエリを実行して、グループ内でのグループ一覧を見つけます。詳細については、「[Operations on groups | Graph API reference (グループに対する操作 | Graph API リファレンス)](/previous-versions/azure/ad/graph/api/groups-operations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="355fb-p113">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](/previous-versions/azure/ad/graph/api/groups-operations).</span></span>
  
### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="355fb-182">Microsoft に連絡してサポートを受ける</span><span class="sxs-lookup"><span data-stu-id="355fb-182">Contacting Microsoft for support</span></span>

<span data-ttu-id="355fb-183">web 用の Office アプリ (Word、Excel など) の使用中にアドインの読み込み中に問題が発生した場合は、Microsoft サポートに問い合わせが必要な場合があります (方法をご覧[ください](../contact-support-for-business-products.md))。</span><span class="sxs-lookup"><span data-stu-id="355fb-183">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../contact-support-for-business-products.md)).</span></span> <span data-ttu-id="355fb-184">サポート チケットに Microsoft 365 環境に関する次の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="355fb-184">Provide the following information about your Microsoft 365 environment in the support ticket.</span></span>
  
|<span data-ttu-id="355fb-185">**プラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="355fb-185">**Platform**</span></span>|<span data-ttu-id="355fb-186">**デバッグ情報**</span><span class="sxs-lookup"><span data-stu-id="355fb-186">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="355fb-187">Office</span><span class="sxs-lookup"><span data-stu-id="355fb-187">Office</span></span>  <br/> | <span data-ttu-id="355fb-188">Charles/Fiddler ログ</span><span class="sxs-lookup"><span data-stu-id="355fb-188">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="355fb-189">テナント ID ( [詳細情報](/onedrive/find-your-office-365-tenant-id.aspx))</span><span class="sxs-lookup"><span data-stu-id="355fb-189">Tenant ID ( [learn how](/onedrive/find-your-office-365-tenant-id.aspx))</span></span>  <br/>  <span data-ttu-id="355fb-190">CorrelationID。</span><span class="sxs-lookup"><span data-stu-id="355fb-190">CorrelationID.</span></span> <span data-ttu-id="355fb-191">1 つの Office ページのソースを表示し、相関 ID の値を探してサポートに送信します。</span><span class="sxs-lookup"><span data-stu-id="355fb-191">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="355fb-192">リッチ クライアント (Windows、Mac)</span><span class="sxs-lookup"><span data-stu-id="355fb-192">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="355fb-193">Charles/Fiddler ログ</span><span class="sxs-lookup"><span data-stu-id="355fb-193">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="355fb-194">クライアント アプリのビルド番号 (できれば **File/Account** のスクリーンショットとして)</span><span class="sxs-lookup"><span data-stu-id="355fb-194">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |
