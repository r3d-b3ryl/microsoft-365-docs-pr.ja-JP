---
title: 組織でアドインの一元展開が機能するかどうかを判断する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Office の365テナントとユーザーが要件を満たしているかどうかを確認します。これにより、一元展開を使用して Office アドインを展開できます。
ms.openlocfilehash: 4351658f2637b86c9b3233f55916d8e0ac0f8cfb
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255052"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="55453-103">組織でアドインの一元展開が機能するかどうかを判断する</span><span class="sxs-lookup"><span data-stu-id="55453-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="55453-104">一元展開は、ほとんどのお客様が office 365 組織内のユーザーやグループに Office アドインを展開するための、推奨される最も豊富な方法です。</span><span class="sxs-lookup"><span data-stu-id="55453-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your Office 365 organization.</span></span> <span data-ttu-id="55453-105">管理者である場合は、このガイダンスを使用して、一括展開を使用できるようにテナントとユーザーが要件を満たしているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="55453-105">If you're an admin, use this guidance to determine if your tenant and users meet the requirements so that you can use Centralized Deployment.</span></span>
<span data-ttu-id="55453-106">一元展開は、Windows、Mac、iOS、Android、およびオンラインの Office アプリをサポートします。</span><span class="sxs-lookup"><span data-stu-id="55453-106">Centralized Deployment supports Windows, Mac, iOS, Android and Online Office apps.</span></span>
<span data-ttu-id="55453-107">すべてのユーザーについて、アドインがクライアントに対して表示されるまでに最大12時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="55453-107">It can take up to 12 hours for an add-in to show up for client for all users.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="55453-108">要件</span><span class="sxs-lookup"><span data-stu-id="55453-108">Requirements</span></span>

<span data-ttu-id="55453-109">アドインを一元展開するには、ユーザーが Office 365 ProPlus (組織 ID を使用して Office にサインインしている) を使用しており、Exchange Online および Exchange Online の Exchange Online メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="55453-109">Centralized deployment of add-ins requires that the users are using Office 365 ProPlus (and are signed into Office using their Organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="55453-110">サブスクリプションの宛先ディレクトリは、に含まれているか、Azure Active Directory にフェデレーションされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="55453-110">Your subscription'd directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="55453-111">以下の Office および Exchange の特定の要件を確認することも、 [office 365 集中展開の互換性チェック](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker)を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="55453-111">You can view specific requirements for Office and Exchange below, or use the [Office 365 Centralized Deployment Compatibility Checker](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="55453-112">一元展開は、次の機能をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="55453-112">Centralized Deployment doesn't support the following:</span></span>
  
- <span data-ttu-id="55453-113">Office 2013 の Word、Excel、または PowerPoint を対象とするアドイン</span><span class="sxs-lookup"><span data-stu-id="55453-113">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span>
    
- <span data-ttu-id="55453-114">オンプレミスのディレクトリ サービス</span><span class="sxs-lookup"><span data-stu-id="55453-114">An on-premises directory service</span></span>
    
- <span data-ttu-id="55453-115">SharePoint に展開するアドイン</span><span class="sxs-lookup"><span data-stu-id="55453-115">Add-in deployment to SharePoint</span></span>  

- <span data-ttu-id="55453-116">Teams アプリ</span><span class="sxs-lookup"><span data-stu-id="55453-116">Teams apps</span></span>
   
- <span data-ttu-id="55453-117">コンポーネント オブジェクト モデル (COM) アドインまたは Visual Studio Tools for Office (VSTO) アドインの展開</span><span class="sxs-lookup"><span data-stu-id="55453-117">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins</span></span>
    
- <span data-ttu-id="55453-118">Office 365 Business などの Exchange を含まない Office 365 の展開</span><span class="sxs-lookup"><span data-stu-id="55453-118">Deployments of Office 365 that do not include Exchange such as Office 365 Business</span></span>

### <a name="office-requirements"></a><span data-ttu-id="55453-119">Office の要件</span><span class="sxs-lookup"><span data-stu-id="55453-119">Office Requirements</span></span>

- <span data-ttu-id="55453-120">Word、Excel、PowerPoint のアドインでは、ユーザーが次のいずれかを使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="55453-120">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="55453-121">Windows デバイスでは、バージョン1704以降の Office 365 ProPlus。</span><span class="sxs-lookup"><span data-stu-id="55453-121">On a Windows device, Version 1704 or later of Office 365 ProPlus.</span></span>
  - <span data-ttu-id="55453-122">Mac では、バージョン15.34 以降。</span><span class="sxs-lookup"><span data-stu-id="55453-122">On a Mac, Version 15.34 or later.</span></span>
      - <span data-ttu-id="55453-123">IOS (iPad のみ)、バージョン2.9.18010804 以降。</span><span class="sxs-lookup"><span data-stu-id="55453-123">On iOS (iPad only), Version 2.9.18010804 or later.</span></span>
- <span data-ttu-id="55453-124">Outlook の場合、ユーザーは次のいずれかを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55453-124">For Outlook, your users must be using one of the following:</span></span> 
  - <span data-ttu-id="55453-125">バージョン1701以降の Office 365 ProPlus。</span><span class="sxs-lookup"><span data-stu-id="55453-125">Version 1701 or later of Office 365 ProPlus.</span></span>
  - <span data-ttu-id="55453-126">バージョン1808以降の Office Professional Plus 2019 または Office Standard 2019。</span><span class="sxs-lookup"><span data-stu-id="55453-126">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="55453-127">16.0.4494.1000 以降のバージョンの Office Professional Plus 2016 (MSI) または Office Standard 2016 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="55453-127">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="55453-128">15.0.4937.1000 以降のバージョンの Office Professional Plus 2013 (MSI) または Office Standard 2013 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="55453-128">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="55453-129">Office 2016 for Mac のバージョン16.0.9318.1000 以降</span><span class="sxs-lookup"><span data-stu-id="55453-129">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span> 
- <span data-ttu-id="55453-130">IOS 版 Outlook mobile のバージョン2.75.0 以降</span><span class="sxs-lookup"><span data-stu-id="55453-130">Version 2.75.0 or later of Outlook mobile for iOS</span></span> 
- <span data-ttu-id="55453-131">Outlook mobile for Android のバージョン2.2.145 以降</span><span class="sxs-lookup"><span data-stu-id="55453-131">Version 2.2.145 or later of Outlook mobile for Android</span></span> 
    
    <span data-ttu-id="55453-132">\* MSI バージョンの Outlook では、[個人用アドイン] セクションではなく、適切な Outlook リボンに管理者がインストールしたアドインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="55453-132">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>
    

#### <a name="find-out-if-office-365-proplus-is-installed"></a><span data-ttu-id="55453-133">Office 365 ProPlus がインストールされているかどうかを調べる</span><span class="sxs-lookup"><span data-stu-id="55453-133">Find out if Office 365 ProPlus is installed</span></span>

<span data-ttu-id="55453-134">Office 365 ProPlus を使用するには、ユーザーは Office 365 アカウントを持っていて、ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="55453-134">To use Office 365 ProPlus, a user must have an Office 365 account and must have been assigned a license.</span></span> <span data-ttu-id="55453-135">詳細については、「[Overview of Office 365 ProPlus (Office 365 ProPlus の概要)](https://go.microsoft.com/fwlink/p/?linkid=846328)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55453-135">For more information, see [Overview of Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=846328).</span></span>

<span data-ttu-id="55453-136">ユーザーが Office 365 ProPlus をインストールしていて、最近使用しているかどうかを検出する最も簡単な方法は、microsoft 365 管理センターで利用できる Microsoft Office ライセンス認証レポートを使用することです。</span><span class="sxs-lookup"><span data-stu-id="55453-136">The simplest way to detect if a user has Office 365 ProPlus installed and has been using it recently is to use the Microsoft Office Activations report, which is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="55453-137">このレポートには、過去 7 日、30 日、90 日、180 日以内に Office 365 ProPlus をライセンス認証したすべてのユーザーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="55453-137">The report provides a list of all users who have activated Office 365 ProPlus within the last 7 days, 30 days, 90 days, or 180 days.</span></span> <span data-ttu-id="55453-138">一元展開をするという目的のため、Windows または Mac のデスクトップで行ったライセンス認証は、レポートの重要な列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="55453-138">For centralized deployment purposes, the desktop activations for Windows or Mac are the important columns in the report.</span></span> <span data-ttu-id="55453-139">このレポートは、Excel にエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="55453-139">You can export the report to Excel.</span></span> <span data-ttu-id="55453-140">レポートについての詳細は、「[管理センターでの Office 365 レポート - Microsoft Office のライセンス認証](../activity-reports/microsoft-office-activations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55453-140">For more information about the report, see [Office 365 Reports in the Admin Center - Microsoft Office activations](../activity-reports/microsoft-office-activations.md).</span></span>
  
<span data-ttu-id="55453-141">ライセンス認証レポートを使用しない場合は、ユーザーが Word などの Office アプリケーションを自分のコンピューターで開くように求めることができます。次に、[**ファイル** \> **アカウント**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="55453-141">If you don't want to use the Activations report, you can ask a user to open an Office application such as Word on their machine, and then choose **File** \> **Account**.</span></span> <span data-ttu-id="55453-142">Under **Product Information**, you should see **Subscription Product** and **Microsoft Office 365 ProPlus**, as shown in the following image.</span><span class="sxs-lookup"><span data-stu-id="55453-142">Under **Product Information**, you should see **Subscription Product** and **Microsoft Office 365 ProPlus**, as shown in the following image.</span></span>

![Office アプリケーションの製品情報](../media/4bff2bb8-0690-4d22-ac1f-b8881807fa39.png)
  
<span data-ttu-id="55453-144">Office 365 ProPlus のヘルプについては、「[Office 365 ProPlus でのトラブルシューティングのヒント](https://go.microsoft.com/fwlink/p/?linkid=846339)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55453-144">For help with Office 365 ProPlus, see [Troubleshooting tips for Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=846339).</span></span>


### <a name="exchange-requirements"></a><span data-ttu-id="55453-145">Exchange の要件</span><span class="sxs-lookup"><span data-stu-id="55453-145">Exchange requirements</span></span>

<span data-ttu-id="55453-p106">Microsoft Exchange では、組織のテナント内にアドイン マニフェストを格納します。管理者が展開するアドインと、ユーザーが受信するアドインは、OAuth 認証をサポートするバージョンの Exchange Server に配置する必要があります。既定では、Exchange マルチテナントと専用の vNext の展開は、OAuth 認証をサポートします。Exchange Dedicated Legacy とハイブリッドのオンプレミス展開は、OAuth 認証をサポートするように構成することができます。ただし、これは既定の構成ではありません。</span><span class="sxs-lookup"><span data-stu-id="55453-p106">Microsoft Exchange stores the add-in manifests within your organization's tenant. The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Server that supports OAuth authentication. By default, Exchange Multi-Tenant and Dedicated VNext deployments support OAuth. Exchange Dedicated Legacy and hybrid on-premises deployments can be configured to support OAuth; however, it isn't the default configuration.</span></span>
  
<span data-ttu-id="55453-p107">組織の Exchange 管理者に、どの構成を使用できるのかを確認してください。ユーザーごとの OAuth 認証接続は、[Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell コマンドレットを使用して、検証できます。</span><span class="sxs-lookup"><span data-stu-id="55453-p107">Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell cmdlet.</span></span> 


### <a name="office-365-centralized-deployment-compatibility-checker"></a><span data-ttu-id="55453-152">Office 365 一元展開の互換性チェック</span><span class="sxs-lookup"><span data-stu-id="55453-152">Office 365 Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="55453-p108">Office 365 一元展開の互換性チェックを使用して、テナントのユーザーが Word、Excel、PowerPoint の一元展開を使用できるように設定されているかどうかを確認できます。互換性チェックは、Outlook のサポートには必要ありません。[ここ](https://aka.ms/officeaddindeploymentorgcompatibilitychecker)から互換性チェックをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="55453-p108">Using the Office 365 Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint. The Compatibility Checker is not required for Outlook support. Download the compatibility checker [here](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>
  
#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="55453-156">互換性チェックを実行する</span><span class="sxs-lookup"><span data-stu-id="55453-156">Run the compatibility checker</span></span>
  
1. <span data-ttu-id="55453-157">管理者特権で PowerShell の .exe ウィンドウを起動します。</span><span class="sxs-lookup"><span data-stu-id="55453-157">Start an elevated PowerShell.exe window.</span></span>
    
2. <span data-ttu-id="55453-158">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="55453-158">Run the following command:</span></span>

```powershell
Import-Module O365CompatibilityChecker
```
    
3. <span data-ttu-id="55453-159">**CompatabilityCheck**コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="55453-159">Run the **Invoke-CompatabilityCheck** command:</span></span>

```powershell
Invoke-CompatibilityCheck
```
   <span data-ttu-id="55453-160">これにより、 *_Tenantdomain_* (たとえば、 *TailspinToysIncorporated</span> ) の入力を求められます。com*) と*_TenantAdmin_* の資格情報 (グローバル管理者の資格情報を使用) を使用して、同意を要求します。</span><span class="sxs-lookup"><span data-stu-id="55453-160">which prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>
    
> [!NOTE]
> <span data-ttu-id="55453-161">テナントのユーザー数によって、チェックが完了するのに数分または数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="55453-161">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span> 
  
<span data-ttu-id="55453-162">ツールの実行が完了すると、コンマ区切り (.csv) 形式で出力ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="55453-162">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="55453-163">既定では、ファイルは**C:\windows\system32**に保存されます。</span><span class="sxs-lookup"><span data-stu-id="55453-163">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="55453-164">出力ファイルには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="55453-164">The output file contains the following information:</span></span>
  
- <span data-ttu-id="55453-165">ユーザー名</span><span class="sxs-lookup"><span data-stu-id="55453-165">User Name</span></span>
    
- <span data-ttu-id="55453-166">ユーザー ID (ユーザーのメール アドレス)</span><span class="sxs-lookup"><span data-stu-id="55453-166">User ID (User's email address)</span></span>
    
- <span data-ttu-id="55453-167">一元展開の準備完了 - 残りの項目が TRUE の場合</span><span class="sxs-lookup"><span data-stu-id="55453-167">Centralized Deployment ready - If the remaining items are true</span></span>
    
- <span data-ttu-id="55453-168">Office プラン-ライセンスが付与されている Office のプラン</span><span class="sxs-lookup"><span data-stu-id="55453-168">Office plan - The plan of Office they are licensed for</span></span>
    
- <span data-ttu-id="55453-169">ライセンス認証された Office - Office をライセンス認証している場合</span><span class="sxs-lookup"><span data-stu-id="55453-169">Office Activated - If they have activated Office</span></span>
    
- <span data-ttu-id="55453-170">サポートされているメールボックス - OAuth 対応メールボックスを使用している場合</span><span class="sxs-lookup"><span data-stu-id="55453-170">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>


  
## <a name="user-and-group-assignments"></a><span data-ttu-id="55453-171">ユーザーとグループの割り当て</span><span class="sxs-lookup"><span data-stu-id="55453-171">User and group assignments</span></span>

<span data-ttu-id="55453-172">現在、一元展開の機能は、Office 365 グループ、配布リスト、セキュリティ グループを含む Azure Active Directory にサポートされているグループの大部分をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="55453-172">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Office 365 Groups, distribution lists, and security groups.</span></span>
  
> [!NOTE]
> <span data-ttu-id="55453-173">メールが有効ではないセキュリティ グループは、現段階ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="55453-173">Non-mail enabled security groups are not currently supported.</span></span> 
  
<span data-ttu-id="55453-174">一元展開では、テナント内の個々のユーザー、グループ、および全員への割り当てがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="55453-174">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="55453-175">一元展開では、最上位のグループまたは親グループのないグループのユーザーがサポートされますが、親グループを持つグループまたはグループのユーザーはネストできません。</span><span class="sxs-lookup"><span data-stu-id="55453-175">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>
   
<span data-ttu-id="55453-p111">次の例では、Sandra、Sheila、「営業部門」のグループがアドインに割り当てられています。「西海岸営業部門」は入れ子のグループのため、Bert と Fred はアドインに割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="55453-p111">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>
  
![営業部門の図](../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="55453-179">グループにネストされたグループが含まれているかどうかを調べる</span><span class="sxs-lookup"><span data-stu-id="55453-179">Find out if a group contains nested groups</span></span>

<span data-ttu-id="55453-180">グループにネストされたグループが含まれているかどうかを調べる最も簡単な方法は、Outlook 内のグループの連絡先カードを確認することです。</span><span class="sxs-lookup"><span data-stu-id="55453-180">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="55453-181">電子メールの [宛先] フィールド**に**グループ名を入力し、解決時にグループ名を選択すると、ユーザーまたはネストしたグループが含まれている場合は、そのグループの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="55453-181">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="55453-182">次の例では、「テスト グループ」での Outlook 情報先カードの [ **メンバー**] タブには、ユーザーはなく、2 つのサブ グループのみが表示されています。</span><span class="sxs-lookup"><span data-stu-id="55453-182">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 
  
![Outlook 連絡先カードの [メンバー] タブ](../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
<span data-ttu-id="55453-p113">反対のクエリを実行できます。グループを解決して、任意のグループのユーザーがいないかどうかを表示します。次の例では、「サブ グループ 1」が「テスト グループ」のメンバーである Outlook 情報先カードの [ **メンバーシップ**] タブの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="55453-p113">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 
  
![Outlook 連絡先カードの [メンバーシップ] タブ](../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
<span data-ttu-id="55453-p114">または、Azure Active Directory Graph API でクエリを実行して、グループ内でのグループ一覧を見つけます。詳細については、「[Operations on groups | Graph API reference (グループに対する操作 | Graph API リファレンス)](https://go.microsoft.com/fwlink/p/?linkid=846342)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55453-p114">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](https://go.microsoft.com/fwlink/p/?linkid=846342).</span></span>
  
### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="55453-189">Microsoft に連絡してサポートを受ける</span><span class="sxs-lookup"><span data-stu-id="55453-189">Contacting Microsoft for support</span></span>

<span data-ttu-id="55453-190">中央で展開された web 用 Office アプリ (Word、Excel など) を使用しているときにアドインの読み込みに問題が発生した場合は、Microsoft サポートに問い合わせる必要があります ([詳細につい](../contact-support-for-business-products.md)ては、「」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="55453-190">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../contact-support-for-business-products.md)).</span></span> <span data-ttu-id="55453-191">サポート チケットで使用している Office 365 環境に関する以下の情報を提供してください。</span><span class="sxs-lookup"><span data-stu-id="55453-191">Provide the following information about your Office 365 environment in the support ticket.</span></span>
  
|<span data-ttu-id="55453-192">**プラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="55453-192">**Platform**</span></span>|<span data-ttu-id="55453-193">**デバッグ情報**</span><span class="sxs-lookup"><span data-stu-id="55453-193">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="55453-194">Office</span><span class="sxs-lookup"><span data-stu-id="55453-194">Office</span></span>  <br/> | <span data-ttu-id="55453-195">Charles/Fiddler ログ</span><span class="sxs-lookup"><span data-stu-id="55453-195">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="55453-196">テナント ID ( [詳細情報](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b.aspx))</span><span class="sxs-lookup"><span data-stu-id="55453-196">Tenant ID ( [learn how](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b.aspx))</span></span>  <br/>  <span data-ttu-id="55453-197">CorrelationID.</span><span class="sxs-lookup"><span data-stu-id="55453-197">CorrelationID.</span></span> <span data-ttu-id="55453-198">いずれかの office ページのソースを表示し、関連付け ID の値を探して、サポートに送信します。</span><span class="sxs-lookup"><span data-stu-id="55453-198">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="55453-199">リッチ クライアント (Windows、Mac)</span><span class="sxs-lookup"><span data-stu-id="55453-199">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="55453-200">Charles/Fiddler ログ</span><span class="sxs-lookup"><span data-stu-id="55453-200">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="55453-201">クライアントアプリのビルド番号 (**ファイル/アカウント**のスクリーンショットとして推奨)</span><span class="sxs-lookup"><span data-stu-id="55453-201">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |
   

