---
title: カスタム ユーザー ビューを作成、編集、削除する
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 4fe7f6ac-be8e-4b57-9e13-24ff889a4b28
description: フィルターを使用して、Microsoft 365 でカスタムユーザービューを作成、編集、または削除する方法について説明します。
ms.openlocfilehash: 265aa1a7c22475710a12a93c2bfee0b7749f438b
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2020
ms.locfileid: "44431643"
---
# <a name="create-edit-or-delete-a-custom-user-view-in-office-365"></a><span data-ttu-id="47094-103">Office 365 でカスタム ユーザー ビューを作成、編集、削除する</span><span class="sxs-lookup"><span data-stu-id="47094-103">Create, edit, or delete a custom user view in Office 365</span></span>

<span data-ttu-id="47094-p101">Office 365 の全体管理者またはユーザー管理の管理者は、一部の特定のユーザーを表示するためのカスタム ユーザー ビューを作成できます。カスタム ユーザー ビューは、Office 365 に付属している標準ビューのセット以外の追加ビューです。カスタム ユーザー ビューは作成、編集、削除でき、ある管理者が作成したカスタム ビューはすべての管理者が使用できます。</span><span class="sxs-lookup"><span data-stu-id="47094-p101">If you're a global or user management admin of Office 365, you can create custom user views to view a specific subset of users. These views are in addition to the standard set of views that come with Office 365. You can create, edit, or delete custom user views, and the custom views you create are available to all admins.</span></span>
  
## <a name="custom-user-views-in-the-admin-center"></a><span data-ttu-id="47094-107">管理センターのカスタムユーザービュー</span><span class="sxs-lookup"><span data-stu-id="47094-107">Custom user views in the admin center</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="47094-108">カスタムユーザービューを作成、編集、または削除すると、組織内のすべての管理者が [**ユーザー** ] ページに移動したときに、その変更内容が**フィルター**一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="47094-108">When you create, edit, or delete a custom user view, the changes will be shown in the **Filter** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="47094-109">最大で 50 個のカスタム ビューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="47094-109">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="47094-110">カスタムユーザービューを作成、編集、または削除すると、組織内のすべての管理者が [**ユーザー** ] ページに移動したときに、その変更内容が [**ビュー** ] ボックスの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="47094-110">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="47094-111">最大で 50 個のカスタム ビューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="47094-111">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="47094-112">カスタムユーザービューを作成、編集、または削除すると、組織内のすべての管理者が [**ユーザー** ] ページに移動したときに、その変更内容が [**ビュー** ] ボックスの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="47094-112">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="47094-113">最大で 50 個のカスタム ビューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="47094-113">You can create up to 50 custom views.</span></span> 

::: moniker-end

> [!TIP]
>  <span data-ttu-id="47094-114">標準ユーザービューは、既定では [**フィルター** ] ボックスの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="47094-114">Standard user views are displayed by default in the **Filters** drop-down list.</span></span> <span data-ttu-id="47094-115">標準フィルターには、**すべてのユーザー**、**ライセンスユーザー**、**ゲストユーザー**、**サインインが許可さ**れた、**サインインがブロック**された、ライセンスのない**ユーザー**、**エラーのあるユーザー、エラーがあるユーザー**、管理**者、\*\*\*\*グローバル管理**者、**ヘルプ管理**者、**サービス**管理**者、ユーザー管理の管理者**が含まれます。</span><span class="sxs-lookup"><span data-stu-id="47094-115">The standard filters include **All users**, **Licensed users**, **Guest users**,  **Sign-in allowed**, **Sign-in blocked**, **Unlicensed users**, **Users with errors**, **Billing admins**, **Global admins**, **Helpdesk admins**, **Service admins**, and **User management admins**.</span></span> <span data-ttu-id="47094-116">標準ビューは編集または削除できません。</span><span class="sxs-lookup"><span data-stu-id="47094-116">You can't edit or delete standard views.</span></span> 

<span data-ttu-id="47094-117">標準ビューに関して次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="47094-117">A few things to note about standard views:</span></span> 

- <span data-ttu-id="47094-p106">一部の標準ビューでは、一覧のユーザー数が 2,000 を超えると、並べ替えられていない一覧が表示されます。このような一覧で特定のユーザーを探すには、検索ボックスを使います。</span><span class="sxs-lookup"><span data-stu-id="47094-p106">Some standard views display an unsorted list if there are more than 2,000 users in the list. To locate specific users in this list, use the search box.</span></span> 
- <span data-ttu-id="47094-120">Microsoft 365 を購入していない場合は、[標準のビュー] ボックスの一覧に [**課金管理者**] が表示されません。</span><span class="sxs-lookup"><span data-stu-id="47094-120">If you didn't purchase Microsoft 365 from Microsoft, **Billing admins** don't appear in the standard views list.</span></span> <span data-ttu-id="47094-121">詳細については、「[管理者ロールを割り当てる](assign-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47094-121">For more information, see [Assigning admin roles](assign-admin-roles.md).</span></span> 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a><span data-ttu-id="47094-122">カスタム ユーザー ビューのフィルターを選択する</span><span class="sxs-lookup"><span data-stu-id="47094-122">Choose the filters for your custom user view</span></span>

<span data-ttu-id="47094-123">カスタム**フィルター**ウィンドウでカスタムビューを作成および編集できます。</span><span class="sxs-lookup"><span data-stu-id="47094-123">You can create and edit your custom views in the **Custom filter** pane.</span></span> <span data-ttu-id="47094-124">複数のフィルター オプションを選択した場合は、選択したすべての条件に一致するユーザーを含む結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="47094-124">If you select multiple filter options, you get results that contain users who match all the selected criteria.</span></span> <span data-ttu-id="47094-125">次の例では、カナダにいる特定のドメイン上のすべてのユーザーを示す "Canadian users" (カナダのユーザー) という名前のカスタム ビューを作成する方法について示します。</span><span class="sxs-lookup"><span data-stu-id="47094-125">The following example shows you how to create a custom view named "Canadian users" that shows all users on a specific domain who are in Canada.</span></span> 

  
 <span data-ttu-id="47094-126">**A-ドメイン**組織に複数のドメインがある場合は、使用可能なドメインのドロップダウンリストから選択できます。</span><span class="sxs-lookup"><span data-stu-id="47094-126">**A - Domain** If you have multiple domains for your organization, you can choose from a drop-down list of domains that are available.</span></span> 
  
 <span data-ttu-id="47094-127">**B-サインイン状態**許可またはブロックされるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="47094-127">**B - Sign-in status** Choose users that are allowed or blocked.</span></span> 
  
 <span data-ttu-id="47094-128">**C-場所**国のドロップダウンリストから場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="47094-128">**C - Location** Choose a location from a drop-down list of countries.</span></span> 
  
 <span data-ttu-id="47094-129">**D で割り当てられた製品ライセンス**組織で利用できるライセンスのドロップダウンリストから選択します。</span><span class="sxs-lookup"><span data-stu-id="47094-129">**D - Assigned product license** Choose from a drop-down list of licenses that are available at your organization.</span></span> <span data-ttu-id="47094-130">選択したライセンスが割り当てられているユーザーを表示するには、このフィルターを使います。</span><span class="sxs-lookup"><span data-stu-id="47094-130">Use this filter to show users who have the license you selected assigned to them.</span></span> <span data-ttu-id="47094-131">ユーザーは追加のライセンスを持っている場合もあります。</span><span class="sxs-lookup"><span data-stu-id="47094-131">Users may also have additional licenses.</span></span> 
  
<span data-ttu-id="47094-132">部門、市区町村、都道府県、国/地域、役職など、組織で使用される追加のユーザー プロファイルの詳細を使ってフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="47094-132">You can also filter by additional user profile details used in your organization such as department, city, state or province, country or region, or job title.</span></span>
  
 <span data-ttu-id="47094-133">**その他の条件:**</span><span class="sxs-lookup"><span data-stu-id="47094-133">**Other conditions:**</span></span>
  
- <span data-ttu-id="47094-134">**同期済みユーザーのみ** アクティブ化されているかどうかにかかわらず、ローカルの Active Directory と同期されているすべてのユーザーを表示するには、このボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="47094-134">**Synchronized users only** Select this box to show all users who have been synced with the local Active Directory, regardless of whether the users have been activated or not.</span></span> 
    
- <span data-ttu-id="47094-135">**エラーのあるユーザー** プロビジョニング エラーがある可能性のあるユーザーを表示するには、このボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="47094-135">**Users with errors** Select this box to show users who may have provisioning errors.</span></span> 
    
- <span data-ttu-id="47094-p110">**ライセンス未付与のユーザー** ライセンスが付与されていないすべてのユーザーを表示するには、このボックスをオンにします。このビューの結果には、Exchange メールボックスは持っていてもライセンスを持たないユーザーも含まれる場合があります。特にこのようなユーザーを追跡するには、[ **Exchange のメールボックスまたはアーカイブはあるがライセンスがないユーザー**] フィルターを使用します。このビューの結果には、Exchange アーカイブは持っていてもライセンスを持たないユーザーも含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="47094-p110">**Unlicensed users** Select this box to find all the users who haven't been assigned a license. The results for this view can also include users who have an Exchange mailbox but don't have a license. To track those users specifically, use the filter **Unlicensed users with Exchange mailboxes or archives**. The results for this view can also include users who have an Exchange archive, but don't have a license.</span></span>
    
- <span data-ttu-id="47094-140">**ライセンスのないユーザーが Exchange メールボックスまたはアーカイブを使用する場合**このチェックボックスをオンにすると、Exchange Online で作成され、Exchange メールボックスを持っているが、Microsoft 365 ライセンスが割り当てられていないユーザーアカウントを表示します。</span><span class="sxs-lookup"><span data-stu-id="47094-140">**Unlicensed users with Exchange mailboxes or archives** Select this box to show user accounts that were created in Exchange Online and have an Exchange mailbox, but weren't assigned an Microsoft 365 license.</span></span> <span data-ttu-id="47094-141">このフィルターの結果には、Exchange アーカイブが割り当てられたユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="47094-141">The results of this filter include users who have or who were assigned an Exchange archive.</span></span> 

> [!NOTE]
> <span data-ttu-id="47094-142">**Exchange メールボックスフィルターを使用してライセンスのないユーザー**は、次の場合に機能します。</span><span class="sxs-lookup"><span data-stu-id="47094-142">The **Unlicensed users with Exchange mailboxes** filter works when:</span></span>
1. <span data-ttu-id="47094-143">メールボックスは、最近**共有**から**ユーザー**に変換されており、ライセンスを持っていません。</span><span class="sxs-lookup"><span data-stu-id="47094-143">The mailbox has been recently converted from **shared** to **user** and it has no license.</span></span>
2. <span data-ttu-id="47094-144">メールボックスは、最近 Microsoft 365 に移行されましたが、ライセンスが割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="47094-144">The mailbox has been recently migrated to Microsoft 365 but a license has not been assigned.</span></span>
3. <span data-ttu-id="47094-145">メールボックスは PowerShell を使用して作成されており、ライセンスが割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="47094-145">The mailbox has been created using PowerShell, and a license has not been assigned.</span></span>
4. <span data-ttu-id="47094-146">オンプレミスで作成された新しいメールボックスが、そのユーザー用にプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="47094-146">A new mailbox that has been created on-premise with a New-RemoteMailbox cmdlet is provisioned for the user.</span></span>
    
> [!TIP]
> <span data-ttu-id="47094-147">2,000 を超えるユーザーを返すカスタム ビューを作成すると、結果のユーザー一覧は並べ替えられません。</span><span class="sxs-lookup"><span data-stu-id="47094-147">If you create a custom view that returns more than 2,000 users, the resulting user list isn't sorted.</span></span> <span data-ttu-id="47094-148">この場合は、検索ボックスを使用してユーザーを検索するか、カスタムビューを編集して検索を絞り込んでください。</span><span class="sxs-lookup"><span data-stu-id="47094-148">In this case, use the search box to find users or edit your custom view to refine your search.</span></span> 
  
## <a name="create-a-custom-user-view"></a><span data-ttu-id="47094-149">カスタムユーザービューを作成する</span><span class="sxs-lookup"><span data-stu-id="47094-149">Create a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="47094-150">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="47094-150">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="47094-151">[**アクティブなユーザー** ] ページで、[**フィルター** ] を選択し、[**新しいフィルター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47094-151">On the **Active users** page, select **Filters** and select **New filter**.</span></span>
  
3. <span data-ttu-id="47094-152">[**カスタムフィルター** ] ページで、フィルターの名前を入力して、カスタムフィルターの条件を選択し、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47094-152">On the **Custom filter** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="47094-153">これで、カスタムビューがフィルターのドロップダウンリストに含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="47094-153">Your custom view is now included in the drop-down list of filters.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="47094-154">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="47094-154">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="47094-155">[**アクティブなユーザー** ] ページで、[**ビュー** ] を選択し、[**カスタムビューの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47094-155">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="47094-156">[**カスタムビュー** ] ページで、フィルターの名前を入力して、カスタムフィルターの条件を選択し、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47094-156">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="47094-157">これで、カスタムビューがフィルターのドロップダウンリストに含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="47094-157">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end


::: moniker range="o365-21vianet"

1. <span data-ttu-id="47094-158">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="47094-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="47094-159">[**アクティブなユーザー** ] ページで、[**ビュー** ] を選択し、[**カスタムビューの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47094-159">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="47094-160">[**カスタムビュー** ] ページで、フィルターの名前を入力して、カスタムフィルターの条件を選択し、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47094-160">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="47094-161">これで、カスタムビューがフィルターのドロップダウンリストに含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="47094-161">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a><span data-ttu-id="47094-162">カスタムユーザービューを編集または削除する</span><span class="sxs-lookup"><span data-stu-id="47094-162">Edit or delete a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="47094-163">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="47094-163">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="47094-164">[**アクティブなユーザー** ] ページで、[**フィルター**] を選択し、変更するフィルターを選択して、[**フィルターの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47094-164">On the **Active users** page, select **Filter**, select the filter you want to change, and then select **Edit filter**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="47094-165">編集できるのはカスタム ビューだけです。</span><span class="sxs-lookup"><span data-stu-id="47094-165">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="47094-166">[**カスタムフィルター** ] ページで、必要に応じて情報を編集し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47094-166">On the **Custom filter** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="47094-167">または、フィルターを削除するには、ページの下部にある [**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47094-167">Or, to delete the filter, at the bottom of the page select **Delete**.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="47094-168">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="47094-168">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="47094-169">[**アクティブなユーザー** ] ページで、[**ビュー**] を選択し、変更するフィルターを選択してから、[**このビューの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47094-169">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="47094-170">編集できるのはカスタム ビューだけです。</span><span class="sxs-lookup"><span data-stu-id="47094-170">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="47094-171">[**カスタムビュー** ] ページで、必要に応じて情報を編集し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47094-171">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="47094-172">または、フィルターを削除するには、ページの下部にある [**カスタムビューの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47094-172">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="47094-173">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="47094-173">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="47094-174">[**アクティブなユーザー** ] ページで、[**ビュー**] を選択し、変更するフィルターを選択してから、[**このビューの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47094-174">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="47094-175">編集できるのはカスタム ビューだけです。</span><span class="sxs-lookup"><span data-stu-id="47094-175">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="47094-176">[**カスタムビュー** ] ページで、必要に応じて情報を編集し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47094-176">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="47094-177">または、フィルターを削除するには、ページの下部にある [**カスタムビューの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47094-177">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end


     