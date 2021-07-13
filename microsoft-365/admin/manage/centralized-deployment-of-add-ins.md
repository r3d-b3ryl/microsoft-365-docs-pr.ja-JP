---
title: 組織でアドインの集中展開が機能するかどうかを判断する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: テナントとユーザーが要件を満たしていることを確認し、集中展開を使用してアドインを展開Officeします。
ms.openlocfilehash: cb1cc019cfd87ee05112ea0ac1f0f1675316c6d3
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393705"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="99269-103">組織でアドインの集中展開が機能するかどうかを判断する</span><span class="sxs-lookup"><span data-stu-id="99269-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="99269-104">集中展開は、ほとんどのお客様が組織内のユーザーやグループに Officeアドインを展開するための、推奨される機能豊富な方法です。</span><span class="sxs-lookup"><span data-stu-id="99269-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your organization.</span></span> <span data-ttu-id="99269-105">管理者の場合は、このガイダンスを使用して、組織とユーザーが要件を満たしていることを確認し、集中展開を使用できます。</span><span class="sxs-lookup"><span data-stu-id="99269-105">If you're an admin, use this guidance to determine if your organization and users meet the requirements so that you can use Centralized Deployment.</span></span>

<span data-ttu-id="99269-106">一元展開には、次のような利点があります。</span><span class="sxs-lookup"><span data-stu-id="99269-106">Centralized Deployment provides the following benefits:</span></span>

- <span data-ttu-id="99269-107">グローバル管理者は、アドインをユーザーに直接割り当て、グループ経由で複数のユーザーに割り当て、組織内のすべてのユーザーに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="99269-107">A Global admin can assign an add-in directly to a user, to multiple users via a group, or to everyone in the organization.</span></span>

- <span data-ttu-id="99269-108">関連するアプリケーションOfficeすると、アドインは自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="99269-108">When the relevant Office application starts, the add-in automatically downloads.</span></span> <span data-ttu-id="99269-109">アドインがアドイン コマンドをサポートしている場合、アドインは自動的にアドイン アプリケーション内のリボンにOfficeされます。</span><span class="sxs-lookup"><span data-stu-id="99269-109">If the add-in supports add-in commands, the add-in automatically appears in the ribbon within the Office application.</span></span>

- <span data-ttu-id="99269-110">管理者がアドインをオフまたは削除した場合、またはユーザーが Azure Active Directory またはアドインが割り当てられているグループから削除された場合、ユーザーのアドインは表示されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="99269-110">Add-ins no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span>

<span data-ttu-id="99269-111">一元展開では、3 つのデスクトップ プラットフォームWindows Mac、および Online Officeできます。</span><span class="sxs-lookup"><span data-stu-id="99269-111">Centralized Deployment supports three desktop platforms Windows, Mac and Online Office apps.</span></span> <span data-ttu-id="99269-112">一元展開では、iOS と Android もサポートしています (Outlook アドインのみ)。</span><span class="sxs-lookup"><span data-stu-id="99269-112">Centralized Deployment also supports iOS and Android (Outlook Mobile Add-ins Only).</span></span>

<span data-ttu-id="99269-113">すべてのユーザーのクライアントにアドインが表示されるには、最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="99269-113">It can take up to 24 hours for an add-in to show up for client for all users.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="99269-114">はじめに</span><span class="sxs-lookup"><span data-stu-id="99269-114">Before you begin</span></span>

<span data-ttu-id="99269-115">アドインの一元展開では、ユーザーが Microsoft 365 Enterprise SKU E3/E5/F3 または Business SKU: Business Basic、Business Standard、Business プレミアム (および組織 ID を使用して Office にサインイン)を使用し、Exchange Online メールボックスとアクティブな Exchange Online メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="99269-115">Centralized deployment of add-ins requires that the users are using Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium (and are signed into Office using their organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="99269-116">サブスクリプション ディレクトリは、サブスクリプション ディレクトリに存在するか、サブスクリプション ディレクトリにAzure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="99269-116">Your subscription directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="99269-117">次の手順に従って、OfficeとExchange要件を確認したり、集中展開の互換性チェックを[使用できます](#centralized-deployment-compatibility-checker)。</span><span class="sxs-lookup"><span data-stu-id="99269-117">You can view specific requirements for Office and Exchange below, or use the [Centralized Deployment Compatibility Checker](#centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="99269-118">一元展開は、次の機能をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="99269-118">Centralized Deployment doesn't support the following:</span></span>

- <span data-ttu-id="99269-119">Office 2013 の Word、Excel、または PowerPoint を対象とするアドイン</span><span class="sxs-lookup"><span data-stu-id="99269-119">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span>
- <span data-ttu-id="99269-120">オンプレミスのディレクトリ サービス</span><span class="sxs-lookup"><span data-stu-id="99269-120">An on-premises directory service</span></span>
- <span data-ttu-id="99269-121">On-Prem メールボックスへのアドインExchange展開</span><span class="sxs-lookup"><span data-stu-id="99269-121">Add-in Deployment to an Exchange On-Prem Mailbox</span></span>
- <span data-ttu-id="99269-122">SharePoint に展開するアドイン</span><span class="sxs-lookup"><span data-stu-id="99269-122">Add-in deployment to SharePoint</span></span>
- <span data-ttu-id="99269-123">Teamsアプリ</span><span class="sxs-lookup"><span data-stu-id="99269-123">Teams apps</span></span>
- <span data-ttu-id="99269-124">コンポーネント オブジェクト モデル (COM) または Visual Studio Tools for Office (VSTO) アドインの展開。</span><span class="sxs-lookup"><span data-stu-id="99269-124">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins.</span></span>
- <span data-ttu-id="99269-125">SKU などのMicrosoft 365を含Exchange Onlineの展開: Microsoft 365 Apps for Business、Microsoft 365 Apps Enterprise。</span><span class="sxs-lookup"><span data-stu-id="99269-125">Deployments of Microsoft 365 that do not include Exchange Online such as SKUs: Microsoft 365 Apps for Business and Microsoft 365 Apps for Enterprise.</span></span>

### <a name="office-requirements"></a><span data-ttu-id="99269-126">Office要件</span><span class="sxs-lookup"><span data-stu-id="99269-126">Office Requirements</span></span>

- <span data-ttu-id="99269-127">Word、Excel、PowerPointアドインの場合、ユーザーは次のいずれかを使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="99269-127">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="99269-128">Windows デバイスのバージョン 1704 以降の Microsoft 365 Enterprise SKU: E3/E5/F3 または Business SKU: Business Basic、Business Standard、Business プレミアム。</span><span class="sxs-lookup"><span data-stu-id="99269-128">On a Windows device, Version 1704 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="99269-129">Mac のバージョン 15.34 以降。</span><span class="sxs-lookup"><span data-stu-id="99269-129">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="99269-130">このOutlook、ユーザーは次のいずれかを使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="99269-130">For Outlook, your users must be using one of the following:</span></span>
  - <span data-ttu-id="99269-131">バージョン 1701 以降の Microsoft 365 Enterprise SKU: E3/E5/F3 または Business SKU: Business Basic、Business Standard、Business プレミアム。</span><span class="sxs-lookup"><span data-stu-id="99269-131">Version 1701 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="99269-132">バージョン 1808 以降のバージョンOffice Professional Plus 2019 2019 Office Standard。</span><span class="sxs-lookup"><span data-stu-id="99269-132">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="99269-133">バージョン 16.0.4494.1000 以降の Office Professional Plus 2016 (MSI) または Office Standard 2016 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="99269-133">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="99269-134">バージョン 15.0.4937.1000 以降の Office Professional Plus 2013 (MSI) または Office Standard (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="99269-134">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="99269-135">バージョン 16.0.9318.1000 以降のバージョンOffice 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="99269-135">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span>
- <span data-ttu-id="99269-136">iOS 用モバイルのバージョン 2.75.0 以降Outlookバージョン 2.75.0 以降</span><span class="sxs-lookup"><span data-stu-id="99269-136">Version 2.75.0 or later of Outlook mobile for iOS</span></span>
- <span data-ttu-id="99269-137">Android 用モバイルのバージョン 2.2.145 Outlook以降</span><span class="sxs-lookup"><span data-stu-id="99269-137">Version 2.2.145 or later of Outlook mobile for Android</span></span>

    <span data-ttu-id="99269-138">\*MSI バージョンの Outlookは、適切な Outlook リボンに管理者がインストールしたアドインを表示します。"My add-ins" セクションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="99269-138">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>

### <a name="exchange-online-requirements"></a><span data-ttu-id="99269-139">Exchange Online要件</span><span class="sxs-lookup"><span data-stu-id="99269-139">Exchange Online requirements</span></span>

<span data-ttu-id="99269-140">Microsoft Exchangeは、組織のテナント内にアドイン マニフェストを格納します。</span><span class="sxs-lookup"><span data-stu-id="99269-140">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="99269-141">アドインを展開する管理者と、それらのアドインを受け取るユーザーは、OAuth 認証をサポートする Exchange Online上にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="99269-141">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>

<span data-ttu-id="99269-p106">組織の Exchange 管理者に、どの構成を使用できるのかを確認してください。ユーザーごとの OAuth 認証接続は、[Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity) PowerShell コマンドレットを使用して、検証できます。</span><span class="sxs-lookup"><span data-stu-id="99269-p106">Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity) PowerShell cmdlet.</span></span>


### <a name="centralized-deployment-compatibility-checker"></a><span data-ttu-id="99269-144">集中展開の互換性チェック</span><span class="sxs-lookup"><span data-stu-id="99269-144">Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="99269-145">集中展開互換性チェッカーを使用して、テナントのユーザーが Word、Excel、および PowerPoint の集中展開を使用するために設定されているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="99269-145">Using the Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint.</span></span> <span data-ttu-id="99269-146">互換性チェックは、サポートをサポートするためにOutlookではありません。</span><span class="sxs-lookup"><span data-stu-id="99269-146">The Compatibility Checker is not required for Outlook support.</span></span> <span data-ttu-id="99269-147">互換性チェック [をダウンロードします](https://aka.ms/officeaddindeploymentorgcompatibilitychecker)。</span><span class="sxs-lookup"><span data-stu-id="99269-147">Download the [compatibility checker](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>

#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="99269-148">互換性チェックを実行する</span><span class="sxs-lookup"><span data-stu-id="99269-148">Run the compatibility checker</span></span>

1. <span data-ttu-id="99269-149">管理者特権のウィンドウPowerShell.exeします。</span><span class="sxs-lookup"><span data-stu-id="99269-149">Start an elevated PowerShell.exe window.</span></span>

2. <span data-ttu-id="99269-150">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="99269-150">Run the following command:</span></span>

   ```powershell
   Import-Module O365CompatibilityChecker
   ```

3. <span data-ttu-id="99269-151">**Invoke-CompatabilityCheck コマンドを実行** します。</span><span class="sxs-lookup"><span data-stu-id="99269-151">Run the **Invoke-CompatabilityCheck** command:</span></span>

   ```powershell
   Invoke-CompatibilityCheck
   ```
   <span data-ttu-id="99269-152">このコマンドは *_、TenantDomain_* *(TailspinToysIncorporated.onmicrosoft など) の入力を求めるプロンプトを表示します。 </span>com)\*\*_および TenantAdmin_* 資格情報 (グローバル管理者資格情報を使用)、同意を要求します。</span><span class="sxs-lookup"><span data-stu-id="99269-152">This command prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>

   > [!NOTE]
   > <span data-ttu-id="99269-153">テナントのユーザー数によって、チェックが完了するのに数分または数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="99269-153">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span>

<span data-ttu-id="99269-154">ツールの実行が完了すると、コンマ区切り (.csv) 形式で出力ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="99269-154">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="99269-155">ファイルは既定で **C:\windows\system32 に** 保存されます。</span><span class="sxs-lookup"><span data-stu-id="99269-155">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="99269-156">出力ファイルには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="99269-156">The output file contains the following information:</span></span>

- <span data-ttu-id="99269-157">ユーザー名</span><span class="sxs-lookup"><span data-stu-id="99269-157">User Name</span></span>

- <span data-ttu-id="99269-158">ユーザー ID (ユーザーのメール アドレス)</span><span class="sxs-lookup"><span data-stu-id="99269-158">User ID (User's email address)</span></span>

- <span data-ttu-id="99269-159">一元展開の準備完了 - 残りの項目が TRUE の場合</span><span class="sxs-lookup"><span data-stu-id="99269-159">Centralized Deployment ready - If the remaining items are true</span></span>

- <span data-ttu-id="99269-160">Officeプラン - ライセンスOfficeのプラン</span><span class="sxs-lookup"><span data-stu-id="99269-160">Office plan - The plan of Office they are licensed for</span></span>

- <span data-ttu-id="99269-161">ライセンス認証された Office - Office をライセンス認証している場合</span><span class="sxs-lookup"><span data-stu-id="99269-161">Office Activated - If they have activated Office</span></span>

- <span data-ttu-id="99269-162">サポートされているメールボックス - OAuth 対応メールボックスを使用している場合</span><span class="sxs-lookup"><span data-stu-id="99269-162">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>

> [!NOTE]
> <span data-ttu-id="99269-163">サーバーの全体展開 PowerShell モジュールを使用する場合、多要素認証はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="99269-163">Multifactor authentication is not supported when using the Central Deployment PowerShell module.</span></span> <span data-ttu-id="99269-164">モジュールは基本認証でのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="99269-164">The module only works with Basic authentication.</span></span>

## <a name="user-and-group-assignments"></a><span data-ttu-id="99269-165">ユーザーとグループの割り当て</span><span class="sxs-lookup"><span data-stu-id="99269-165">User and group assignments</span></span>

<span data-ttu-id="99269-166">集中展開機能は、現在、Azure Active Directory、配布リスト、セキュリティ グループなど、Microsoft 365でサポートされているグループの大部分をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="99269-166">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Microsoft 365 groups, distribution lists, and security groups.</span></span>

> [!NOTE]
> <span data-ttu-id="99269-167">メールが有効ではないセキュリティ グループは、現段階ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="99269-167">Non-mail enabled security groups are not currently supported.</span></span>

<span data-ttu-id="99269-168">集中展開は、テナント内の個々のユーザー、グループ、およびすべてのユーザーへの割り当てをサポートします。</span><span class="sxs-lookup"><span data-stu-id="99269-168">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="99269-169">集中展開は、上位レベルのグループまたは親グループのないグループのユーザーをサポートしますが、ネストされたグループまたは親グループを持つグループのユーザーはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="99269-169">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>

<span data-ttu-id="99269-p111">次の例では、Sandra、Sheila、「営業部門」のグループがアドインに割り当てられています。「西海岸営業部門」は入れ子のグループのため、Bert と Fred はアドインに割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="99269-p111">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>

![営業部門の図](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)


### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="99269-173">グループにネストされたグループが含まれているかどうかを調べる</span><span class="sxs-lookup"><span data-stu-id="99269-173">Find out if a group contains nested groups</span></span>

<span data-ttu-id="99269-174">グループにネストされたグループが含まれているかどうかを調べる最も簡単な方法は、Outlook 内のグループの連絡先カードを確認することです。</span><span class="sxs-lookup"><span data-stu-id="99269-174">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="99269-175">電子メールの **[To]** フィールドにグループ名を入力し、解決時にグループ名を選択すると、グループ名にユーザーまたは入れ子になったグループが含まれているかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="99269-175">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="99269-176">次の例では、「テスト グループ」での Outlook 情報先カードの [ **メンバー**] タブには、ユーザーはなく、2 つのサブ グループのみが表示されています。</span><span class="sxs-lookup"><span data-stu-id="99269-176">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span>

![連絡先カードの [Outlook] タブ](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)

<span data-ttu-id="99269-p113">反対のクエリを実行できます。グループを解決して、任意のグループのユーザーがいないかどうかを表示します。次の例では、「サブ グループ 1」が「テスト グループ」のメンバーである Outlook 情報先カードの [ **メンバーシップ**] タブの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="99269-p113">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span>

![連絡先カードの [Outlook] タブ](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)

<span data-ttu-id="99269-p114">または、Azure Active Directory Graph API でクエリを実行して、グループ内でのグループ一覧を見つけます。詳細については、「[Operations on groups | Graph API reference (グループに対する操作 | Graph API リファレンス)](/previous-versions/azure/ad/graph/api/groups-operations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99269-p114">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](/previous-versions/azure/ad/graph/api/groups-operations).</span></span>

### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="99269-183">Microsoft に連絡してサポートを受ける</span><span class="sxs-lookup"><span data-stu-id="99269-183">Contacting Microsoft for support</span></span>

<span data-ttu-id="99269-184">web 用の Office アプリ (Word、Excel など) の使用中にアドインの読み込み中に問題が発生した場合は、Microsoft サポートに連絡する必要があります (方法を[](../../business-video/get-help-support.md)確認してください)。</span><span class="sxs-lookup"><span data-stu-id="99269-184">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../../business-video/get-help-support.md)).</span></span> <span data-ttu-id="99269-185">サポート チケットに、ユーザーのMicrosoft 365情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="99269-185">Provide the following information about your Microsoft 365 environment in the support ticket.</span></span>

|<span data-ttu-id="99269-186">**プラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="99269-186">**Platform**</span></span>|<span data-ttu-id="99269-187">**デバッグ情報**</span><span class="sxs-lookup"><span data-stu-id="99269-187">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="99269-188">Office</span><span class="sxs-lookup"><span data-stu-id="99269-188">Office</span></span>  <br/> | <span data-ttu-id="99269-189">Charles/Fiddler ログ</span><span class="sxs-lookup"><span data-stu-id="99269-189">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="99269-190">テナント ID ([方法の詳細](/onedrive/find-your-office-365-tenant-id))</span><span class="sxs-lookup"><span data-stu-id="99269-190">Tenant ID ([learn how](/onedrive/find-your-office-365-tenant-id))</span></span>  <br/>  <span data-ttu-id="99269-191">CorrelationID。</span><span class="sxs-lookup"><span data-stu-id="99269-191">CorrelationID.</span></span> <span data-ttu-id="99269-192">1 つの Office ページのソースを表示し、相関 ID の値を探してサポートに送信します。</span><span class="sxs-lookup"><span data-stu-id="99269-192">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="99269-193">リッチ クライアント (Windows、Mac)</span><span class="sxs-lookup"><span data-stu-id="99269-193">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="99269-194">Charles/Fiddler ログ</span><span class="sxs-lookup"><span data-stu-id="99269-194">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="99269-195">クライアント アプリのビルド番号 (できれば **File/Account** のスクリーンショットとして)</span><span class="sxs-lookup"><span data-stu-id="99269-195">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |

## <a name="related-content"></a><span data-ttu-id="99269-196">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="99269-196">Related content</span></span>

<span data-ttu-id="99269-197">[管理センターにアドインを展開](../manage/manage-deployment-of-add-ins.md) する (記事)</span><span class="sxs-lookup"><span data-stu-id="99269-197">[Deploy add-ins in the admin center](../manage/manage-deployment-of-add-ins.md) (article)</span></span>\
<span data-ttu-id="99269-198">[管理センターでアドインを管理](manage-addins-in-the-admin-center.md) する (記事)</span><span class="sxs-lookup"><span data-stu-id="99269-198">[Manage add-ins in the admin center](manage-addins-in-the-admin-center.md) (article)</span></span>\
<span data-ttu-id="99269-199">[集中展開に関する FAQ](../manage/centralized-deployment-faq.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="99269-199">[Centralized Deployment FAQ](../manage/centralized-deployment-faq.md) (article)</span></span>\
<span data-ttu-id="99269-200">[ビジネス ユーザー Microsoft 365最新の Officeクライアント](../setup/upgrade-users-to-latest-office-client.md)にアップグレードする (記事)</span><span class="sxs-lookup"><span data-stu-id="99269-200">[Upgrade your Microsoft 365 for business users to the latest Office client](../setup/upgrade-users-to-latest-office-client.md) (article)</span></span>
 