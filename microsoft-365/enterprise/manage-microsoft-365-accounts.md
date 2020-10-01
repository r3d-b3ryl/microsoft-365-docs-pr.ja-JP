---
title: Microsoft 365 ユーザーアカウントの管理
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Microsoft 365 のユーザーアカウントを管理する方法について説明します。
ms.openlocfilehash: a7b6d89a0f66605dde168b85d74fcd8e513afc15
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327761"
---
# <a name="manage-microsoft-365-user-accounts"></a><span data-ttu-id="e1bfd-103">Microsoft 365 ユーザーアカウントの管理</span><span class="sxs-lookup"><span data-stu-id="e1bfd-103">Manage Microsoft 365 user accounts</span></span>

<span data-ttu-id="e1bfd-104">Microsoft 365 ユーザーアカウントは、構成に応じて、いくつかの異なる方法で管理できます。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-104">You can manage Microsoft 365 user accounts in several different ways, depending on your configuration.</span></span> <span data-ttu-id="e1bfd-105">ユーザーアカウントは、 [Microsoft 365 管理センター](https://docs.microsoft.com/microsoft-365/admin/add-users/)、 [PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)、Active DIRECTORY ドメインサービス (AD DS)、または Azure ACTIVE directory (azure AD) 管理ポータルで管理できます。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-105">You can manage user accounts in the [Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/add-users/), [PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md), in Active Directory Domain Services (AD DS), or in the Azure Active Directory (Azure AD) admin portal.</span></span> 

<span data-ttu-id="e1bfd-106">Microsoft 365 を購入するとすぐに、Microsoft 365 管理センターと PowerShell を使用してアカウントを管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-106">As soon as you purchase Microsoft 365, the Microsoft 365 admin center and PowerShell can be used to manage accounts.</span></span> <span data-ttu-id="e1bfd-107">クラウド id を管理する場合、組織内のすべてのユーザーが個別のユーザーアカウント名とパスワードを持っています。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-107">When managing cloud identities, every person in your organization has a separate user account name and password.</span></span> <span data-ttu-id="e1bfd-108">オンプレミスのインフラストラクチャと統合して、ユーザーアカウントを Microsoft 365 と同期させる場合は、Azure AD Connect を使用して、シングルサインオン (SSO) 機能の id とパスワードの同期を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-108">If you want to integrate with your on-premises infrastructure and have user accounts synchronized with Microsoft 365, you can use Azure AD Connect to provide synchronization of identities and passwords for single sign-on (SSO) functionality.</span></span>
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a><span data-ttu-id="e1bfd-109">ユーザーアカウントを管理する場所と方法を計画します。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-109">Plan for where and how you will manage your user accounts</span></span>

<span data-ttu-id="e1bfd-110">ユーザーアカウントを管理する場所と方法は、Microsoft 365 で使用する id モデルによって異なります。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-110">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="e1bfd-111">これらのモデル全体は、クラウド専用でハイブリッドです。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-111">The two overall models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="e1bfd-112">クラウド専用</span><span class="sxs-lookup"><span data-stu-id="e1bfd-112">Cloud-only</span></span>

<span data-ttu-id="e1bfd-113">Microsoft 365 管理センターでユーザーを作成して管理します。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-113">You create and manage users in the Microsoft 365 admin center.</span></span> <span data-ttu-id="e1bfd-114">PowerShell または Azure AD 管理センターを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-114">You can also use PowerShell or the Azure AD admin center.</span></span> 
    
### <a name="hybrid"></a><span data-ttu-id="e1bfd-115">ハイブリッド</span><span class="sxs-lookup"><span data-stu-id="e1bfd-115">Hybrid</span></span>

<span data-ttu-id="e1bfd-116">ユーザーアカウントは、AD DS から Microsoft 365 と同期されるので、オンプレミスの AD DS ツールを使用してユーザーアカウントを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-116">User accounts are synchronized with Microsoft 365 from AD DS, so you must use on-premises AD DS tools to manage user accounts.</span></span> 
    
## <a name="managing-accounts"></a><span data-ttu-id="e1bfd-117">アカウントの管理</span><span class="sxs-lookup"><span data-stu-id="e1bfd-117">Managing Accounts</span></span>

<span data-ttu-id="e1bfd-118">組織がアカウントを作成および管理する方法を決定するときは、次の要件を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-118">When deciding which way your organization will create and manage accounts, consider the following requirements:</span></span>
  
- <span data-ttu-id="e1bfd-119">Microsoft 365 と AD DS 間で id を接続するには、ディレクトリ同期ソフトウェアを社内環境内のサーバーにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-119">The directory synchronization software needs to be installed on servers within your on-premises environment to connect the identities between Microsoft 365 and your AD DS.</span></span>
    
- <span data-ttu-id="e1bfd-120">SSO オプションを含むディレクトリ同期オプションでは、AD DS 属性が標準に適合している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-120">Any directory synchronization option, including SSO options, requires that your AD DS attributes meet standards.</span></span> <span data-ttu-id="e1bfd-121">ディレクトリで使用される属性の詳細と、必要に応じてクリーンアップを行う方法については、「 [Microsoft 365 へのディレクトリ同期の準備](prepare-for-directory-synchronization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-121">The specifics of what attributes are used in your directory and what cleanup (if any) is needed are described in [Prepare for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md).</span></span> 
    
- <span data-ttu-id="e1bfd-122">Microsoft 365 アカウントを作成する方法を計画します。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-122">Plan how you are going to create Microsoft 365 accounts.</span></span>
    
<span data-ttu-id="e1bfd-123">次の表に、さまざまなアカウント管理ツールを示します。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-123">The following table lists the different account management tools.</span></span>
    
|<span data-ttu-id="e1bfd-124">ツール</span><span class="sxs-lookup"><span data-stu-id="e1bfd-124">Tool</span></span>|<span data-ttu-id="e1bfd-125">Notes</span><span class="sxs-lookup"><span data-stu-id="e1bfd-125">Notes</span></span>|
|:-----|:-----|
|<span data-ttu-id="e1bfd-126">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="e1bfd-126">Microsoft 365 admin center</span></span>  <br/> |[<span data-ttu-id="e1bfd-127">ユーザーを個別にまたは一括して追加する</span><span class="sxs-lookup"><span data-stu-id="e1bfd-127">Add users individually or in bulk</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) <br/>  <span data-ttu-id="e1bfd-128">ユーザーアカウントを追加および変更するための簡単な web インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-128">Provides a simple web interface to add and change user accounts.</span></span>  <br/>  <span data-ttu-id="e1bfd-129">ディレクトリ同期が有効になっている場合、ユーザーの変更には使用できません (場所およびライセンスの割り当てを設定できます)。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-129">Can't be used to change users if directory synchronization is enabled (location and license assignment can be set).</span></span>  <br/>  <span data-ttu-id="e1bfd-130">SSO オプションを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-130">Can't be used with SSO options.</span></span>  <br/> |
|<span data-ttu-id="e1bfd-131">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1bfd-131">Windows PowerShell</span></span>  <br/> |[<span data-ttu-id="e1bfd-132">Windows PowerShell を使用して Microsoft 365 を管理する</span><span class="sxs-lookup"><span data-stu-id="e1bfd-132">Manage Microsoft 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=698471) <br/>  <span data-ttu-id="e1bfd-133">Windows PowerShell スクリプトを使用して、ユーザーを一括ユーザーで追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-133">Allows you to add users in bulk users by using a Windows PowerShell script.</span></span>  <br/>  <span data-ttu-id="e1bfd-134">アカウントの作成方法に関係なく、アカウントに場所とライセンスを割り当てるために使用できます。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-134">Can be used to assign location and licenses to accounts, regardless of how the accounts are created.</span></span>  <br/> |
|<span data-ttu-id="e1bfd-135">一括インポート</span><span class="sxs-lookup"><span data-stu-id="e1bfd-135">Bulk import</span></span>  <br/> |[<span data-ttu-id="e1bfd-136">同時に複数のユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="e1bfd-136">Add several users at the same time</span></span>](add-several-users-at-the-same-time.md) <br/>  <span data-ttu-id="e1bfd-137">CSV ファイルをインポートして、ユーザーのグループを Microsoft 365 に追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-137">Allows you to import a CSV file to add a group of users to Microsoft 365.</span></span>  <br/>  <span data-ttu-id="e1bfd-138">SSO オプションを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-138">Can't be used with SSO options.</span></span>  <br/> |
|<span data-ttu-id="e1bfd-139">Azure AD</span><span class="sxs-lookup"><span data-stu-id="e1bfd-139">Azure AD</span></span>  <br/> |<span data-ttu-id="e1bfd-140">Microsoft 365 のサブスクリプションを使用して、Azure AD の無料版を入手できます。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-140">You get a free edition of Azure AD with your Microsoft 365 subscription.</span></span> <span data-ttu-id="e1bfd-141">クラウドユーザーのセルフサービスによるパスワードのリセットなどの機能を実行したり、無料版を使用してサインインページとアクセスパネルページをカスタマイズしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-141">You can perform functions like self-service password reset for cloud users, and customization of the Sign-in and Access Panel pages by using the free edition.</span></span> <span data-ttu-id="e1bfd-142">拡張機能を利用するには、basic edition、Azure AD Premium P1、または Azure AD Premium P2 にアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-142">To get enhanced functionality, you can upgrade to the basic edition, Azure AD Premium P1, or Azure AD Premium P2.</span></span> <span data-ttu-id="e1bfd-143">サポートされている機能の一覧については、「 [AZURE AD エディション](https://go.microsoft.com/fwlink/p/?LinkId=698465) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-143">See [Azure AD editions](https://go.microsoft.com/fwlink/p/?LinkId=698465) for the list of supported features.</span></span>  <br/> |
|<span data-ttu-id="e1bfd-144">ディレクトリ同期</span><span class="sxs-lookup"><span data-stu-id="e1bfd-144">Directory synchronization</span></span>  <br/> |[<span data-ttu-id="e1bfd-145">オンプレミス id と Azure AD の統合</span><span class="sxs-lookup"><span data-stu-id="e1bfd-145">Integrating your on-premises identities with Azure AD</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=624168) <br/>  <span data-ttu-id="e1bfd-146">パスワード同期の有無にかかわらずディレクトリ同期を行うには、 [AZURE AD Connect with express settings](https://go.microsoft.com/fwlink/p/?LinkID=698537)を使用します。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-146">For directory synchronization with or without password synchronization, use [Azure AD Connect with express settings](https://go.microsoft.com/fwlink/p/?LinkID=698537).</span></span>  <br/>  <span data-ttu-id="e1bfd-147">複数のフォレストおよび SSO オプションでは、 [AZURE AD Connect のカスタムインストール](https://go.microsoft.com/fwlink/p/?LinkId=698430)を使用します。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-147">For multiple forests and SSO options, use [Custom Installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).</span></span>  <br/>  <span data-ttu-id="e1bfd-148">SSO を有効にするために必要なインフラストラクチャを提供します。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-148">Provides the infrastructure that's necessary to enable SSO.</span></span>  <br/>  <span data-ttu-id="e1bfd-149">段階的な移行やハイブリッド Exchange などの多くのハイブリッドシナリオに必要</span><span class="sxs-lookup"><span data-stu-id="e1bfd-149">Required for many hybrid scenarios such as staged migration and hybrid Exchange</span></span>  <br/>  <span data-ttu-id="e1bfd-150">セキュリティおよびメールが有効なグループを AD DS から同期します。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-150">Synchronizes security and mail-enabled groups from your AD DS.</span></span>  <br/> |
|||
   
- <span data-ttu-id="e1bfd-151">ユーザーアカウントを Microsoft 365 に追加する方法に関係なく、ライセンスの割り当て、場所の指定など、いくつかのアカウント機能を管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-151">Regardless of how you intend to add the user accounts to Microsoft 365, you need to manage several account features, such as assigning licenses, specifying location, and so on.</span></span> <span data-ttu-id="e1bfd-152">これらの機能は、Microsoft 365 管理センターから長期間において管理することも、 [PowerShell を使用してユーザーアカウントを作成](https://go.microsoft.com/fwlink/p/?LinkId=717083)することもできます。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-152">These features can be managed long-term from the Microsoft 365 admin center or you can also [create user accounts with PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=717083).</span></span>
    
    <span data-ttu-id="e1bfd-153">管理センターを使用してすべてのユーザーの追加と管理を選択する場合は、Microsoft 365 アカウントを作成するときと同時に、場所を指定してライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-153">If you choose to add and manage all your users through the admin center, you will specify the location and assign licenses at the same time as creating the Microsoft 365 account.</span></span> <span data-ttu-id="e1bfd-154">そのため、計画はあまり必要ありません。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-154">As a result, not much planning is required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e1bfd-155">Microsoft 365 で、ライセンスを割り当てずに (たとえば SharePoint Online に) アカウントを作成することは、アカウント所有者が Microsoft 365 center を表示できるが、会社のサブスクリプション内のサービスにアクセスできないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-155">Creating accounts in Microsoft 365 without assigning a license (to SharePoint Online, for example) means that the account owner can view the Microsoft 365 center but can't access any of the services within your company's subscription.</span></span> <span data-ttu-id="e1bfd-156">場所とライセンスを割り当てた後、割り当てたサービスにアカウントがレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-156">After you assign a location and the license, the account is replicated to the service or services that you assigned.</span></span> <span data-ttu-id="e1bfd-157">ユーザーは、自分のアカウントにサインインして、自分に割り当てられているサービスを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e1bfd-157">The user can sign in to their account and use the services that you assigned to them.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e1bfd-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1bfd-158">See also</span></span>

[<span data-ttu-id="e1bfd-159">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="e1bfd-159">Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users)

[<span data-ttu-id="e1bfd-160">PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1bfd-160">PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)  
