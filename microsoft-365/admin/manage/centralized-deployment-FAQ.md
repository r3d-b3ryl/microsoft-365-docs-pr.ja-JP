---
title: 一元展開に関する FAQ
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365 管理センターからの一元展開についてよく寄せられる質問に対する回答を確認してください。
ms.openlocfilehash: b1b5ccbb5373bf5d536208efdfe487bc0c872f25
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2020
ms.locfileid: "45102886"
---
# <a name="centralized-deployment-faq"></a><span data-ttu-id="27fdc-103">一元展開に関する FAQ</span><span class="sxs-lookup"><span data-stu-id="27fdc-103">Centralized Deployment FAQ</span></span>

<span data-ttu-id="27fdc-104">一元展開は、Office 365 管理者が Office アドイン (Word、Excel、PowerPoint、および Outlook) を組織内のユーザーとグループに展開する場合に推奨される方法です。これは、この記事で説明されているように、一元展開を使用するためのすべての要件を組織が満たしている場合です。</span><span class="sxs-lookup"><span data-stu-id="27fdc-104">Centralized Deployment is the recommended way for an Office 365 admin to deploy Office add-ins (Word, Excel, PowerPoint, and Outlook) to users and groups within an organization, provided the organization meets all requirements for using Centralized Deployment as outlined in this article.</span></span>   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a><span data-ttu-id="27fdc-105">組織で一元展開が設定されているかどうかを確認する方法</span><span class="sxs-lookup"><span data-stu-id="27fdc-105">How do I know if my organization is set up for Centralized Deployment?</span></span>  

<span data-ttu-id="27fdc-106">アドインを一元展開するには、ユーザーが Microsoft 365 Apps for enterprise (組織のログイン資格情報を使用して Office にサインインしている) を使用しており、Exchange Online メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="27fdc-106">Centralized deployment of add-ins requires that users are using Microsoft 365 Apps for enterprise (and are signed into Office using their organizational log-in credentials) and have Exchange Online mailboxes.</span></span> <span data-ttu-id="27fdc-107">サブスクリプションディレクトリは、Azure Active Directory に存在するか、フェデレーションされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="27fdc-107">Your subscription directory must either be in, or federated to, Azure Active Directory.</span></span>  
 
<span data-ttu-id="27fdc-108">一元展開は、オンラインメールボックスでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="27fdc-108">Centralized Deployment is only supported for online mailboxes.</span></span> <span data-ttu-id="27fdc-109">オンプレミスの Exchange メールボックスへの展開はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="27fdc-109">It does not support deployment to on-premises Exchange mailboxes.</span></span>

<span data-ttu-id="27fdc-110">[一元展開の互換性チェック](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)   を使用して、サブスクリプションが対象になるかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="27fdc-110">You can use the [Centralized Deployment Compatibility Checker](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker) to determine if your subscription is eligible.</span></span> 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a><span data-ttu-id="27fdc-111">一元展開を使用してアドインユーザーの割り当てをどのように対象にしていますか。</span><span class="sxs-lookup"><span data-stu-id="27fdc-111">How do you target add-in user assignments with Centralized Deployment?</span></span>  

<span data-ttu-id="27fdc-112">一元展開では、テナント内の個々のユーザー、グループ、および全員への割り当てがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="27fdc-112">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="27fdc-113">階層型展開は、最上位のグループまたは親グループのないグループのユーザーに使用できますが、親グループを持つグループまたはグループのユーザーには使用できません。</span><span class="sxs-lookup"><span data-stu-id="27fdc-113">Centralized Deployment can be used for users in top-level groups or groups without parent groups, but not for users in nested groups or groups that have parent groups.</span></span> <span data-ttu-id="27fdc-114">一元展開は、Office 365 グループ、配布リスト、セキュリティグループなど、ほとんどの Azure Active Directory グループの一部でもあります。</span><span class="sxs-lookup"><span data-stu-id="27fdc-114">Centralized Deployment is also part of most Azure Active Directory groups, including Office 365 Groups, distribution lists, and security groups.</span></span>  

<span data-ttu-id="27fdc-115">管理を容易にするには、個別のユーザー割り当てではなく、グループの割り当てを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="27fdc-115">It is better to use groups assignments instead of individual user assignment for easier management.</span></span>
 
<span data-ttu-id="27fdc-116">詳細については、「[ユーザーとグループの割り当て](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27fdc-116">For more details, see [User and Group assignments](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments).</span></span>  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a><span data-ttu-id="27fdc-117">アドインがすべてのユーザーに対して表示されるまでにどのくらいの時間がかかりますか?</span><span class="sxs-lookup"><span data-stu-id="27fdc-117">How long does it take for add-ins to show up for all users?</span></span>  

<span data-ttu-id="27fdc-118">すべてのユーザーに対してアドインが表示されるまでに最大24時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="27fdc-118">It can take up to 24 hours for an add-in to show up for all users.</span></span> <span data-ttu-id="27fdc-119">これには、アドインの更新に対して同じ時間、オン/オフの切り替え、またはアドインの削除による変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="27fdc-119">It can take the same amount of time for add-in updates, changes from turn on or turn off, or add-in removals.</span></span> 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a><span data-ttu-id="27fdc-120">管理者として、組織のアドインへのユーザーアクセスを管理するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="27fdc-120">As an administrator, how do I manage the user access to add-ins for my organization?</span></span>

<span data-ttu-id="27fdc-121">ユーザー、グループ、または組織全体にアドインを簡単に展開するには、管理者が一元展開を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="27fdc-121">For easy deployment of add-ins to users, groups, or to your entire organization, we recommend administrators use Centralized Deployment.</span></span>

<span data-ttu-id="27fdc-122">ユーザーアクセスの管理の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27fdc-122">For more information about managing user access, see:</span></span>
 - [<span data-ttu-id="27fdc-123">すべてのクライアント (Outlook を除く) で Office ストアをオフにして、アドインのダウンロードを禁止する</span><span class="sxs-lookup"><span data-stu-id="27fdc-123">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [<span data-ttu-id="27fdc-124">Outlook 用のアドインをインストールおよび管理できる管理者とユーザーを指定する</span><span class="sxs-lookup"><span data-stu-id="27fdc-124">Specify the administrators and users who can install and manage add-ins for Outlook</span></span>](https://docs.microsoft.com/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a><span data-ttu-id="27fdc-125">一元展開によって、管理者は Outlook アドインの展開方法を柔軟に選択できるようになりますか。</span><span class="sxs-lookup"><span data-stu-id="27fdc-125">Will Centralized Deployment provide admins the flexibility to choose the deployment method for Outlook add-ins?</span></span>  

<span data-ttu-id="27fdc-126">はい。</span><span class="sxs-lookup"><span data-stu-id="27fdc-126">Yes.</span></span> <span data-ttu-id="27fdc-127">一元展開を使用すると、管理者はアドインの展開時に Outlook アドインの3つの展開方法のうちの1つを柔軟に選択できます。</span><span class="sxs-lookup"><span data-stu-id="27fdc-127">Centralized Deployment provides admins the flexibility to choose one of three deployment methods for Outlook add-ins during add-in deployment:</span></span>

<span data-ttu-id="27fdc-128">**Fixed (既定値)**  アドインは、割り当てられたユーザーに自動的に展開され、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="27fdc-128">**Fixed (Default)**  The add-in is deployed automatically to the assigned users, and they cannot remove it.</span></span>  
 
<span data-ttu-id="27fdc-129">**利用可能**ユーザーは、[ホーム] を選択してアドインを Outlook にインストールし、管理者によって管理されたアドイン **> >** します。</span><span class="sxs-lookup"><span data-stu-id="27fdc-129">**Available** Users can install the add-in in Outlook by choosing **Home > Get More add-ins > Admin-managed**.</span></span>
 
<span data-ttu-id="27fdc-130">**省略可能**アドインは、割り当てられたユーザーに自動的に展開されますが、削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="27fdc-130">**Optional** The add-in is deployed automatically to the assigned users, but they can choose to remove it.</span></span>  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a><span data-ttu-id="27fdc-131">管理者は基幹業務 (LOB) アドインを更新できますか?</span><span class="sxs-lookup"><span data-stu-id="27fdc-131">Can admins update Line-of-Business (LOB) add-ins?</span></span>  

<span data-ttu-id="27fdc-132">はい。</span><span class="sxs-lookup"><span data-stu-id="27fdc-132">Yes.</span></span> <span data-ttu-id="27fdc-133">管理者が展開した LOB アドインのメタデータ変更をサポートするために、管理者は新しいマニフェストファイルをアップロードできます。アドインは、次に Office アプリケーションが起動したときに更新されます。</span><span class="sxs-lookup"><span data-stu-id="27fdc-133">Admins can upload a new manifest file to support metadata changes for admin-deployed LOB add-ins. The add-in updates the next time the Office applications starts.</span></span> <span data-ttu-id="27fdc-134">Web アプリケーションはいつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="27fdc-134">The web application can change at any time.</span></span>  
 
<span data-ttu-id="27fdc-135">詳細については、「[基幹業務アドイン](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#more-about-office-add-ins-security)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27fdc-135">For more information, see [line-of-business add-in](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#more-about-office-add-ins-security).</span></span>  

## <a name="can-admins-turn-off-add-ins"></a><span data-ttu-id="27fdc-136">管理者がアドインをオフにできるか</span><span class="sxs-lookup"><span data-stu-id="27fdc-136">Can admins turn off add-ins?</span></span>  

<span data-ttu-id="27fdc-137">はい。</span><span class="sxs-lookup"><span data-stu-id="27fdc-137">Yes.</span></span> <span data-ttu-id="27fdc-138">管理者は、Microsoft 管理センターからすべてのユーザーに対して展開するアドインをオンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="27fdc-138">Admins can turn on or off the add-ins they deploy for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="27fdc-139">詳細については、「[アドインの状態](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#add-in-states)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27fdc-139">For more information, see [Add-in states](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#add-in-states).</span></span>  

##  <a name="can-admins-delete-or-remove-add-ins"></a><span data-ttu-id="27fdc-140">管理者がアドインを削除または削除できるかどうか。</span><span class="sxs-lookup"><span data-stu-id="27fdc-140">Can admins delete or remove add-ins?</span></span>

<span data-ttu-id="27fdc-141">はい。</span><span class="sxs-lookup"><span data-stu-id="27fdc-141">Yes.</span></span> <span data-ttu-id="27fdc-142">管理者は、Microsoft 管理センターからすべてのユーザー向けに展開したアドインを削除できます。</span><span class="sxs-lookup"><span data-stu-id="27fdc-142">Admins can delete add-ins they deployed for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="27fdc-143">詳細については、「[アドインを削除する](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#delete-an-add-in)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27fdc-143">For more information, see [Delete an add-in](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#delete-an-add-in).</span></span> 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a><span data-ttu-id="27fdc-144">管理者は一元展開を使用して、Office ストアから有料のアドインを展開できますか。</span><span class="sxs-lookup"><span data-stu-id="27fdc-144">Can admins deploy paid add-ins from the Office Store using Centralized Deployment?</span></span> 

<span data-ttu-id="27fdc-145">いいえ。</span><span class="sxs-lookup"><span data-stu-id="27fdc-145">No.</span></span> <span data-ttu-id="27fdc-146">現時点では、一元展開を使用して、Office ストアから有料のアドインを展開することはできません。</span><span class="sxs-lookup"><span data-stu-id="27fdc-146">You can't deploy paid add-ins from the Office Store using Centralized Deployment at this time.</span></span>  
 
<span data-ttu-id="27fdc-147">マニフェストファイルまたは URL を要求するには、有料アドインの ISV 開発者に確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="27fdc-147">We suggest reaching out to the ISV Developer for the paid add-in to request a manifest file or a URL.</span></span> <span data-ttu-id="27fdc-148">テナント管理者は、一元展開を使用して、アドインを LOB アドインとして展開できます。</span><span class="sxs-lookup"><span data-stu-id="27fdc-148">The tenant admin can then deploy the add-in as a LOB add-in using Centralized Deployment.</span></span>
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a><span data-ttu-id="27fdc-149">組織のアドインを管理するには、どの管理者の役割を使用する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="27fdc-149">Which admin role do I need to manage add-ins for my organization?</span></span>  

<span data-ttu-id="27fdc-150">アドインを管理するには、グローバル管理者の役割を持っている必要があります。Microsoft 365 for business サブスクリプションを購入したユーザーである場合は、グローバル管理者になります。</span><span class="sxs-lookup"><span data-stu-id="27fdc-150">You must have the Global admin role to manage add-ins. If you're the person who purchased your Microsoft 365 for business subscription, you are the Global admin.</span></span> 
 
<span data-ttu-id="27fdc-151">サブスクリプションには、組織内の他のユーザーに割り当てることができる一連の管理者ロールが付属しています。</span><span class="sxs-lookup"><span data-stu-id="27fdc-151">Your subscription comes with a set of admin roles that you can assign to other users in your organization.</span></span> <span data-ttu-id="27fdc-152">各管理役割は、一般的なビジネス機能にマップされ、組織内のユーザーに Microsoft 365 管理センターで特定のタスクを実行するためのアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="27fdc-152">Each admin role maps to common business functions and gives people in your organization permissions to perform specific tasks in the Microsoft 365 admin center.</span></span>  
 
<span data-ttu-id="27fdc-153">詳細については、「[管理者ロールを割り当てる](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27fdc-153">For more information, see [Assign admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span></span>  
