---
title: 一元展開に関する FAQ
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 管理センターから集中展開に関するよくある質問Microsoft 365確認します。
ms.openlocfilehash: 60d7a91da738803976b6823009450124d7b57814
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579304"
---
# <a name="centralized-deployment-faq"></a><span data-ttu-id="2ccaf-103">一元展開に関する FAQ</span><span class="sxs-lookup"><span data-stu-id="2ccaf-103">Centralized Deployment FAQ</span></span>

<span data-ttu-id="2ccaf-104">Office 365 管理者が組織内のユーザーとグループに Office アドイン (Word、Excel、PowerPoint、および Outlook) を展開する場合は、この記事で説明した集中展開を使用するためのすべての要件を満たしている場合に、集中展開が推奨されます。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-104">Centralized Deployment is the recommended way for an Office 365 admin to deploy Office add-ins (Word, Excel, PowerPoint, and Outlook) to users and groups within an organization, provided the organization meets all requirements for using Centralized Deployment as outlined in this article.</span></span>   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a><span data-ttu-id="2ccaf-105">組織が集中展開用に設定されているかどうかは、どのように確認できますか?</span><span class="sxs-lookup"><span data-stu-id="2ccaf-105">How do I know if my organization is set up for Centralized Deployment?</span></span>  

<span data-ttu-id="2ccaf-106">アドインの一元的な展開では、ユーザーが Microsoft 365 Apps for enterprise を使用し (組織のログイン資格情報を使用して Office にサインインしている) 必要があります。また、Exchange Online メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-106">Centralized deployment of add-ins requires that users are using Microsoft 365 Apps for enterprise (and are signed into Office using their organizational log-in credentials) and have Exchange Online mailboxes.</span></span> <span data-ttu-id="2ccaf-107">サブスクリプション ディレクトリは、サブスクリプション ディレクトリ内にあるか、またはフェデレーションされている必要Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-107">Your subscription directory must either be in, or federated to, Azure Active Directory.</span></span>  
 
<span data-ttu-id="2ccaf-108">集中展開は、オンライン メールボックスでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-108">Centralized Deployment is only supported for online mailboxes.</span></span> <span data-ttu-id="2ccaf-109">オンプレミスのメールボックスへの展開はExchangeされません。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-109">It does not support deployment to on-premises Exchange mailboxes.</span></span>

<span data-ttu-id="2ccaf-110">集中展開互換性[チェッカーを使用して](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)   、サブスクリプションが適格かどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-110">You can use the [Centralized Deployment Compatibility Checker](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker) to determine if your subscription is eligible.</span></span> 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a><span data-ttu-id="2ccaf-111">集中展開を使用してアドインのユーザー割り当てをターゲットに設定する方法</span><span class="sxs-lookup"><span data-stu-id="2ccaf-111">How do you target add-in user assignments with Centralized Deployment?</span></span>  

<span data-ttu-id="2ccaf-112">集中展開は、テナント内の個々のユーザー、グループ、およびすべてのユーザーへの割り当てをサポートします。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-112">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="2ccaf-113">集中展開は、上位レベルのグループまたは親グループのないグループのユーザーには使用できますが、ネストされたグループまたは親グループを持つグループのユーザーには使用できません。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-113">Centralized Deployment can be used for users in top-level groups or groups without parent groups, but not for users in nested groups or groups that have parent groups.</span></span> <span data-ttu-id="2ccaf-114">集中展開は、グループ、配布リストAzure Active Directoryセキュリティ グループなど、Office 365グループの一部です。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-114">Centralized Deployment is also part of most Azure Active Directory groups, including Office 365 Groups, distribution lists, and security groups.</span></span>  

<span data-ttu-id="2ccaf-115">管理を容易にするために、個々のユーザー割り当てではなくグループ割り当てを使用する方が良いです。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-115">It is better to use groups assignments instead of individual user assignment for easier management.</span></span>
 
<span data-ttu-id="2ccaf-116">詳細については、「ユーザーと [グループの割り当て」を参照してください](./centralized-deployment-of-add-ins.md?view=o365-worldwide#user-and-group-assignments)。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-116">For more details, see [User and Group assignments](./centralized-deployment-of-add-ins.md?view=o365-worldwide#user-and-group-assignments).</span></span>  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a><span data-ttu-id="2ccaf-117">アドインがすべてのユーザーに表示されるのにどれくらいの時間が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="2ccaf-117">How long does it take for add-ins to show up for all users?</span></span>  

<span data-ttu-id="2ccaf-118">アドインがすべてのユーザーに表示するには、最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-118">It can take up to 24 hours for an add-in to show up for all users.</span></span> <span data-ttu-id="2ccaf-119">アドインの更新、オンまたはオフからの変更、アドインの削除に同じ時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-119">It can take the same amount of time for add-in updates, changes from turn on or turn off, or add-in removals.</span></span> 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a><span data-ttu-id="2ccaf-120">管理者として、組織のアドインへのユーザー アクセスを管理する方法</span><span class="sxs-lookup"><span data-stu-id="2ccaf-120">As an administrator, how do I manage the user access to add-ins for my organization?</span></span>

<span data-ttu-id="2ccaf-121">ユーザー、グループ、または組織全体にアドインを簡単に展開するには、管理者が集中展開を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-121">For easy deployment of add-ins to users, groups, or to your entire organization, we recommend administrators use Centralized Deployment.</span></span>

<span data-ttu-id="2ccaf-122">ユーザー アクセスの管理の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-122">For more information about managing user access, see:</span></span>
 - [<span data-ttu-id="2ccaf-123">すべてのクライアントで Office ストアをオフにしてアドインのダウンロードを防止する (Outlook を除く)</span><span class="sxs-lookup"><span data-stu-id="2ccaf-123">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>](./manage-addins-in-the-admin-center.md#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [<span data-ttu-id="2ccaf-124">Outlook 用のアドインをインストールおよび管理できる管理者とユーザーを指定する</span><span class="sxs-lookup"><span data-stu-id="2ccaf-124">Specify the administrators and users who can install and manage add-ins for Outlook</span></span>](/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a><span data-ttu-id="2ccaf-125">一元展開では、管理者はアドインの展開方法を柔軟に選択Outlook提供されますか?</span><span class="sxs-lookup"><span data-stu-id="2ccaf-125">Will Centralized Deployment provide admins the flexibility to choose the deployment method for Outlook add-ins?</span></span>  

<span data-ttu-id="2ccaf-126">はい。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-126">Yes.</span></span> <span data-ttu-id="2ccaf-127">一元展開では、管理者は、アドインの展開中に、Outlookアドインの 3 つの展開方法のいずれかを柔軟に選択できます。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-127">Centralized Deployment provides admins the flexibility to choose one of three deployment methods for Outlook add-ins during add-in deployment:</span></span>

<span data-ttu-id="2ccaf-128">**固定 (既定)**  アドインは割り当てられたユーザーに自動的に展開され、削除できません。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-128">**Fixed (Default)**  The add-in is deployed automatically to the assigned users, and they cannot remove it.</span></span>  
 
<span data-ttu-id="2ccaf-129">**使用可能** ユーザーは、[ホーム] を選択して Outlookアドインをインストール>管理者が管理>**アドインを取得します**。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-129">**Available** Users can install the add-in in Outlook by choosing **Home > Get More add-ins > Admin-managed**.</span></span>
 
<span data-ttu-id="2ccaf-130">**省略可能** アドインは割り当てられたユーザーに自動的に展開されますが、削除を選択できます。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-130">**Optional** The add-in is deployed automatically to the assigned users, but they can choose to remove it.</span></span>  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a><span data-ttu-id="2ccaf-131">管理者は、LINE-of-Business (LOB) アドインを更新できますか?</span><span class="sxs-lookup"><span data-stu-id="2ccaf-131">Can admins update Line-of-Business (LOB) add-ins?</span></span>  

<span data-ttu-id="2ccaf-132">はい。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-132">Yes.</span></span> <span data-ttu-id="2ccaf-133">管理者は、管理者が展開した LOB アドインのメタデータ変更をサポートするために、新しいマニフェスト ファイルをアップロードできます。アドインは、次にアプリケーションを起動Office更新します。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-133">Admins can upload a new manifest file to support metadata changes for admin-deployed LOB add-ins. The add-in updates the next time the Office applications starts.</span></span> <span data-ttu-id="2ccaf-134">Web アプリケーションはいつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-134">The web application can change at any time.</span></span>  
 
<span data-ttu-id="2ccaf-135">詳細については [、「line-of-business アドイン」を参照してください](./manage-addins-in-the-admin-center.md)。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-135">For more information, see [line-of-business add-in](./manage-addins-in-the-admin-center.md).</span></span>  

## <a name="can-admins-turn-off-add-ins"></a><span data-ttu-id="2ccaf-136">管理者はアドインをオフにできますか?</span><span class="sxs-lookup"><span data-stu-id="2ccaf-136">Can admins turn off add-ins?</span></span>  

<span data-ttu-id="2ccaf-137">はい。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-137">Yes.</span></span> <span data-ttu-id="2ccaf-138">管理者は、Microsoft 管理センターからすべてのユーザーに展開するアドインをオンまたはオフにできます。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-138">Admins can turn on or off the add-ins they deploy for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="2ccaf-139">詳細については、「アドインの [状態」を参照してください](./manage-addins-in-the-admin-center.md#add-in-states)。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-139">For more information, see [Add-in states](./manage-addins-in-the-admin-center.md#add-in-states).</span></span>  

##  <a name="can-admins-delete-or-remove-add-ins"></a><span data-ttu-id="2ccaf-140">管理者はアドインを削除または削除できますか?</span><span class="sxs-lookup"><span data-stu-id="2ccaf-140">Can admins delete or remove add-ins?</span></span>

<span data-ttu-id="2ccaf-141">はい。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-141">Yes.</span></span> <span data-ttu-id="2ccaf-142">管理者は、Microsoft 管理センターからすべてのユーザーに展開したアドインを削除できます。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-142">Admins can delete add-ins they deployed for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="2ccaf-143">詳細については、「Delete [an add-in」を参照してください](./manage-addins-in-the-admin-center.md#delete-an-add-in)。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-143">For more information, see [Delete an add-in](./manage-addins-in-the-admin-center.md#delete-an-add-in).</span></span> 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a><span data-ttu-id="2ccaf-144">管理者は、集中展開を使用して、Officeストアから有料アドインを展開できますか?</span><span class="sxs-lookup"><span data-stu-id="2ccaf-144">Can admins deploy paid add-ins from the Office Store using Centralized Deployment?</span></span> 

<span data-ttu-id="2ccaf-145">いいえ。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-145">No.</span></span> <span data-ttu-id="2ccaf-146">現時点では、集中展開を使用して、Officeストアから有料アドインを展開できます。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-146">You can't deploy paid add-ins from the Office Store using Centralized Deployment at this time.</span></span>  
 
<span data-ttu-id="2ccaf-147">マニフェスト ファイルまたは URL を要求するには、有料アドインの ISV 開発者に手を差し伸べることです。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-147">We suggest reaching out to the ISV Developer for the paid add-in to request a manifest file or a URL.</span></span> <span data-ttu-id="2ccaf-148">テナント管理者は、集中展開を使用して、アドインを LOB アドインとして展開できます。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-148">The tenant admin can then deploy the add-in as a LOB add-in using Centralized Deployment.</span></span>
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a><span data-ttu-id="2ccaf-149">組織のアドインを管理するために必要な管理者の役割は何ですか?</span><span class="sxs-lookup"><span data-stu-id="2ccaf-149">Which admin role do I need to manage add-ins for my organization?</span></span>  

<span data-ttu-id="2ccaf-150">グローバル管理者は、アドイン管理ライフサイクルへの完全なアクセス権を持つ推奨される役割です。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-150">Global Admin is the recommended role with complete access to add-in management lifecycle.</span></span> <span data-ttu-id="2ccaf-151">他の管理者の役割では、アドイン展開ライフサイクルへのアクセスが制限されています。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-151">Other Admin roles have a limited access to add-in deployment lifecycle.</span></span> <span data-ttu-id="2ccaf-152">ビジネス サブスクリプション用にMicrosoft 365したユーザーは、グローバル管理者です。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-152">If you're the person who purchased your Microsoft 365 for business subscription, you are the Global admin.</span></span> 
 
<span data-ttu-id="2ccaf-153">サブスクリプションには、組織内の他のユーザーに割り当て可能な一連の管理者ロールが付属しています。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-153">Your subscription comes with a set of admin roles that you can assign to other users in your organization.</span></span> <span data-ttu-id="2ccaf-154">各管理者の役割は、一般的なビジネス機能にマップされ、組織内のユーザーが管理センターで特定のタスクを実行Microsoft 365します。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-154">Each admin role maps to common business functions and gives people in your organization permissions to perform specific tasks in the Microsoft 365 admin center.</span></span>  
 
<span data-ttu-id="2ccaf-155">詳細については、「管理者ロールの割り [当て」を参照してください](../add-users/assign-admin-roles.md?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="2ccaf-155">For more information, see [Assign admin roles](../add-users/assign-admin-roles.md?view=o365-worldwide).</span></span> 