---
title: ユーザー Microsoft 365を管理する
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
description: ユーザー アカウントを管理するMicrosoft 365を確認します。
ms.openlocfilehash: c0387bf50228e0eeb763b4807b15c8d57e02eeac
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909564"
---
# <a name="manage-microsoft-365-user-accounts"></a><span data-ttu-id="58896-103">ユーザー Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="58896-103">Manage Microsoft 365 user accounts</span></span>

<span data-ttu-id="58896-104">構成に応Microsoft 365、さまざまな方法でユーザー アカウントを管理できます。</span><span class="sxs-lookup"><span data-stu-id="58896-104">You can manage Microsoft 365 user accounts in several different ways, depending on your configuration.</span></span> <span data-ttu-id="58896-105">ユーザー アカウントは[、Microsoft 365](../admin/add-users/index.yml)管理センター [、PowerShell、Active](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)Directory ドメイン サービス (AD DS)、または Azure Active Directory (Azure AD) 管理ポータルで管理できます。</span><span class="sxs-lookup"><span data-stu-id="58896-105">You can manage user accounts in the [Microsoft 365 admin center](../admin/add-users/index.yml), [PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md), in Active Directory Domain Services (AD DS), or in the Azure Active Directory (Azure AD) admin portal.</span></span> 

<span data-ttu-id="58896-106">アカウントを購入するとすぐにMicrosoft 365管理センター Microsoft 365 PowerShell を使用してアカウントを管理できます。</span><span class="sxs-lookup"><span data-stu-id="58896-106">As soon as you purchase Microsoft 365, the Microsoft 365 admin center and PowerShell can be used to manage accounts.</span></span> <span data-ttu-id="58896-107">クラウド ID を管理する場合、組織内のすべてのユーザーには、個別のユーザー アカウント名とパスワードがあります。</span><span class="sxs-lookup"><span data-stu-id="58896-107">When managing cloud identities, every person in your organization has a separate user account name and password.</span></span> <span data-ttu-id="58896-108">オンプレミスインフラストラクチャと統合し、Microsoft 365 とユーザー アカウントを同期する場合は、Azure AD Connect を使用してシングル サインオン (SSO) 機能の ID とパスワードの同期を提供できます。</span><span class="sxs-lookup"><span data-stu-id="58896-108">If you want to integrate with your on-premises infrastructure and have user accounts synchronized with Microsoft 365, you can use Azure AD Connect to provide synchronization of identities and passwords for single sign-on (SSO) functionality.</span></span>
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a><span data-ttu-id="58896-109">ユーザー アカウントの管理場所と管理方法を計画する</span><span class="sxs-lookup"><span data-stu-id="58896-109">Plan for where and how you will manage your user accounts</span></span>

<span data-ttu-id="58896-110">ユーザー アカウントを管理する場所と方法は、ユーザー アカウントに使用する id モデルによってMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="58896-110">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="58896-111">2 つの全体的なモデルは、クラウド専用とハイブリッドです。</span><span class="sxs-lookup"><span data-stu-id="58896-111">The two overall models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="58896-112">クラウド専用</span><span class="sxs-lookup"><span data-stu-id="58896-112">Cloud-only</span></span>

<span data-ttu-id="58896-113">管理者センターでユーザーを作成Microsoft 365管理します。</span><span class="sxs-lookup"><span data-stu-id="58896-113">You create and manage users in the Microsoft 365 admin center.</span></span> <span data-ttu-id="58896-114">PowerShell または Azure の管理センター AD使用できます。</span><span class="sxs-lookup"><span data-stu-id="58896-114">You can also use PowerShell or the Azure AD admin center.</span></span> 
    
### <a name="hybrid"></a><span data-ttu-id="58896-115">ハイブリッド</span><span class="sxs-lookup"><span data-stu-id="58896-115">Hybrid</span></span>

<span data-ttu-id="58896-116">ユーザー アカウントは DS からMicrosoft 365 ADされます。そのため、ユーザー アカウントを管理するには、オンプレミスの DS ADを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58896-116">User accounts are synchronized with Microsoft 365 from AD DS, so you must use on-premises AD DS tools to manage user accounts.</span></span> 
    
## <a name="managing-accounts"></a><span data-ttu-id="58896-117">アカウントの管理</span><span class="sxs-lookup"><span data-stu-id="58896-117">Managing Accounts</span></span>

<span data-ttu-id="58896-118">組織でアカウントを作成および管理する方法を決定する場合は、次の要件を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="58896-118">When deciding which way your organization will create and manage accounts, consider the following requirements:</span></span>
  
- <span data-ttu-id="58896-119">ディレクトリ同期ソフトウェアは、オンプレミス環境内のサーバーにインストールして、MICROSOFT 365 DS と ADする必要があります。</span><span class="sxs-lookup"><span data-stu-id="58896-119">The directory synchronization software needs to be installed on servers within your on-premises environment to connect the identities between Microsoft 365 and your AD DS.</span></span>
    
- <span data-ttu-id="58896-120">SSO オプションを含む任意のディレクトリ同期オプションでは、DS 属性がADを満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="58896-120">Any directory synchronization option, including SSO options, requires that your AD DS attributes meet standards.</span></span> <span data-ttu-id="58896-121">ディレクトリで使用する属性と、必要なクリーンアップ (存在する場合) の詳細については、「ディレクトリ同期の準備からディレクトリへの同期の準備」[をMicrosoft 365。](prepare-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="58896-121">The specifics of what attributes are used in your directory and what cleanup (if any) is needed are described in [Prepare for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md).</span></span> 
    
- <span data-ttu-id="58896-122">アカウントの作成方法を計画Microsoft 365します。</span><span class="sxs-lookup"><span data-stu-id="58896-122">Plan how you are going to create Microsoft 365 accounts.</span></span>
    
<span data-ttu-id="58896-123">次の表に、さまざまなアカウント管理ツールの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="58896-123">The following table lists the different account management tools.</span></span>
    
|<span data-ttu-id="58896-124">ツール</span><span class="sxs-lookup"><span data-stu-id="58896-124">Tool</span></span>|<span data-ttu-id="58896-125">備考</span><span class="sxs-lookup"><span data-stu-id="58896-125">Notes</span></span>|
|:-----|:-----|
|<span data-ttu-id="58896-126">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="58896-126">Microsoft 365 admin center</span></span>  <br/> |[<span data-ttu-id="58896-127">ユーザーを個別または一括で追加する</span><span class="sxs-lookup"><span data-stu-id="58896-127">Add users individually or in bulk</span></span>](../admin/add-users/add-users.md) <br/>  <span data-ttu-id="58896-128">ユーザー アカウントを追加および変更する簡単な Web インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="58896-128">Provides a simple web interface to add and change user accounts.</span></span>  <br/>  <span data-ttu-id="58896-129">ディレクトリ同期が有効になっている場合は、ユーザーを変更することはできません (場所とライセンスの割り当てを設定できます)。</span><span class="sxs-lookup"><span data-stu-id="58896-129">Can't be used to change users if directory synchronization is enabled (location and license assignment can be set).</span></span>  <br/>  <span data-ttu-id="58896-130">SSO オプションでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="58896-130">Can't be used with SSO options.</span></span>  <br/> |
|<span data-ttu-id="58896-131">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="58896-131">Windows PowerShell</span></span>  <br/> |[<span data-ttu-id="58896-132">管理Microsoft 365を使用Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="58896-132">Manage Microsoft 365 with Windows PowerShell</span></span>](./manage-microsoft-365-with-microsoft-365-powershell.md) <br/>  <span data-ttu-id="58896-133">カスタム スクリプトを使用して、一括ユーザーにユーザーをWindows PowerShellできます。</span><span class="sxs-lookup"><span data-stu-id="58896-133">Allows you to add users in bulk users by using a Windows PowerShell script.</span></span>  <br/>  <span data-ttu-id="58896-134">アカウントの作成方法に関係なく、場所とライセンスをアカウントに割り当てる場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="58896-134">Can be used to assign location and licenses to accounts, regardless of how the accounts are created.</span></span>  <br/> |
|<span data-ttu-id="58896-135">一括インポート</span><span class="sxs-lookup"><span data-stu-id="58896-135">Bulk import</span></span>  <br/> |[<span data-ttu-id="58896-136">同時に複数のユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="58896-136">Add several users at the same time</span></span>](add-several-users-at-the-same-time.md) <br/>  <span data-ttu-id="58896-137">CSV ファイルをインポートして、ユーザーのグループをユーザーグループに追加Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="58896-137">Allows you to import a CSV file to add a group of users to Microsoft 365.</span></span>  <br/>  <span data-ttu-id="58896-138">SSO オプションでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="58896-138">Can't be used with SSO options.</span></span>  <br/> |
|<span data-ttu-id="58896-139">Azure AD</span><span class="sxs-lookup"><span data-stu-id="58896-139">Azure AD</span></span>  <br/> |<span data-ttu-id="58896-140">サブスクリプションを使用して Azure AD無料版Microsoft 365取得します。</span><span class="sxs-lookup"><span data-stu-id="58896-140">You get a free edition of Azure AD with your Microsoft 365 subscription.</span></span> <span data-ttu-id="58896-141">無料版を使用すると、クラウド ユーザーのセルフサービス パスワードのリセット、サインイン ページとアクセス パネル ページのカスタマイズなど、機能を実行できます。</span><span class="sxs-lookup"><span data-stu-id="58896-141">You can perform functions like self-service password reset for cloud users, and customization of the Sign-in and Access Panel pages by using the free edition.</span></span> <span data-ttu-id="58896-142">拡張機能を取得するには、基本エディション、Azure AD プレミアム P1、または Azure AD プレミアム P2 にアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="58896-142">To get enhanced functionality, you can upgrade to the basic edition, Azure AD Premium P1, or Azure AD Premium P2.</span></span> <span data-ttu-id="58896-143">サポート [されている機能のADについては、「Azure](/azure/active-directory/fundamentals/active-directory-whatis) AD エディション」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58896-143">See [Azure AD editions](/azure/active-directory/fundamentals/active-directory-whatis) for the list of supported features.</span></span>  <br/> |
|<span data-ttu-id="58896-144">ディレクトリ同期</span><span class="sxs-lookup"><span data-stu-id="58896-144">Directory synchronization</span></span>  <br/> |[<span data-ttu-id="58896-145">オンプレミス ID と Azure id の統合AD</span><span class="sxs-lookup"><span data-stu-id="58896-145">Integrating your on-premises identities with Azure AD</span></span>](/azure/active-directory/hybrid/whatis-hybrid-identity) <br/>  <span data-ttu-id="58896-146">パスワード同期を使用するかしないディレクトリ同期の場合は、[高速AD Connect Azure AD Connectを使用します](/azure/active-directory/hybrid/how-to-connect-install-express)。</span><span class="sxs-lookup"><span data-stu-id="58896-146">For directory synchronization with or without password synchronization, use [Azure AD Connect with express settings](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>  <br/>  <span data-ttu-id="58896-147">複数のフォレストと SSO オプションの場合は[、Azure サーバーの](/azure/active-directory/hybrid/how-to-connect-install-custom)カスタム インストールを使用AD Connect。</span><span class="sxs-lookup"><span data-stu-id="58896-147">For multiple forests and SSO options, use [Custom Installation of Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).</span></span>  <br/>  <span data-ttu-id="58896-148">SSO を有効にするために必要なインフラストラクチャを提供します。</span><span class="sxs-lookup"><span data-stu-id="58896-148">Provides the infrastructure that's necessary to enable SSO.</span></span>  <br/>  <span data-ttu-id="58896-149">ステージ移行やハイブリッド 移行など、多くのハイブリッド シナリオで必要Exchange</span><span class="sxs-lookup"><span data-stu-id="58896-149">Required for many hybrid scenarios such as staged migration and hybrid Exchange</span></span>  <br/>  <span data-ttu-id="58896-150">セキュリティとメールが有効なグループを DS から同期ADします。</span><span class="sxs-lookup"><span data-stu-id="58896-150">Synchronizes security and mail-enabled groups from your AD DS.</span></span>  <br/> |
|||
   
- <span data-ttu-id="58896-151">Microsoft 365 にユーザー アカウントを追加する方法に関係なく、ライセンスの割り当て、場所の指定など、いくつかのアカウント機能を管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58896-151">Regardless of how you intend to add the user accounts to Microsoft 365, you need to manage several account features, such as assigning licenses, specifying location, and so on.</span></span> <span data-ttu-id="58896-152">これらの機能は、管理センターから長期的に管理Microsoft 365、PowerShell を使用してユーザー アカウント[を作成することもできます](./create-user-accounts-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="58896-152">These features can be managed long-term from the Microsoft 365 admin center or you can also [create user accounts with PowerShell](./create-user-accounts-with-microsoft-365-powershell.md).</span></span>
    
    <span data-ttu-id="58896-153">管理センターを通じてすべてのユーザーを追加および管理する場合は、場所を指定し、ユーザー アカウントの作成と同時にライセンスを割りMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="58896-153">If you choose to add and manage all your users through the admin center, you will specify the location and assign licenses at the same time as creating the Microsoft 365 account.</span></span> <span data-ttu-id="58896-154">その結果、あまり計画が必要ありません。</span><span class="sxs-lookup"><span data-stu-id="58896-154">As a result, not much planning is required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="58896-155">Microsoft 365 でライセンスを割り当てずに (SharePoint Online に) アカウントを作成すると、アカウント所有者は Microsoft 365 センターを表示できますが、会社のサブスクリプション内のサービスにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="58896-155">Creating accounts in Microsoft 365 without assigning a license (to SharePoint Online, for example) means that the account owner can view the Microsoft 365 center but can't access any of the services within your company's subscription.</span></span> <span data-ttu-id="58896-156">場所とライセンスを割り当てた後、アカウントは割り当てたサービスまたはサービスにレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="58896-156">After you assign a location and the license, the account is replicated to the service or services that you assigned.</span></span> <span data-ttu-id="58896-157">ユーザーは自分のアカウントにサインインし、割り当てたサービスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="58896-157">The user can sign in to their account and use the services that you assigned to them.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="58896-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="58896-158">See also</span></span>

[<span data-ttu-id="58896-159">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="58896-159">Microsoft 365 admin center</span></span>](../admin/add-users/index.yml)

[<span data-ttu-id="58896-160">PowerShell</span><span class="sxs-lookup"><span data-stu-id="58896-160">PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)