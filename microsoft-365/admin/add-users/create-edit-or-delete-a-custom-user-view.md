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
description: フィルターを使用して、Microsoft 365 でカスタム ユーザー ビューを作成、編集、または削除する方法について説明します。
ms.openlocfilehash: 4bd4ea351612c2ae5175cd27fa7a689d671a8b62
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51755574"
---
# <a name="create-edit-or-delete-a-custom-user-view"></a><span data-ttu-id="280c1-103">カスタム ユーザー ビューを作成、編集、削除する</span><span class="sxs-lookup"><span data-stu-id="280c1-103">Create, edit, or delete a custom user view</span></span>

<span data-ttu-id="280c1-104">Microsoft 365 for business サブスクリプションのグローバルまたはユーザー管理管理者の場合は、カスタム ユーザー ビューを作成して、ユーザーの特定のサブセットを表示できます。</span><span class="sxs-lookup"><span data-stu-id="280c1-104">If you're a global or user management admin of a Microsoft 365 for business subscription,  you can create custom user views to view a specific subset of users.</span></span> <span data-ttu-id="280c1-105">これらのビューは、標準のビューセットに加えて表示されます。</span><span class="sxs-lookup"><span data-stu-id="280c1-105">These views are in addition to the standard set of views.</span></span> <span data-ttu-id="280c1-106">カスタム ユーザー ビューは作成、編集、削除でき、ある管理者が作成したカスタム ビューはすべての管理者が使用できます。</span><span class="sxs-lookup"><span data-stu-id="280c1-106">You can create, edit, or delete custom user views, and the custom views you create are available to all admins.</span></span>
  
## <a name="custom-user-views-in-the-admin-center"></a><span data-ttu-id="280c1-107">管理センターのカスタム ユーザー ビュー</span><span class="sxs-lookup"><span data-stu-id="280c1-107">Custom user views in the admin center</span></span>

<span data-ttu-id="280c1-108">カスタム ユーザー ビューを作成、編集、または削除すると、変更が [ユーザー]ページに移動すると、会社のすべての管理者が表示するフィルター リスト **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="280c1-108">When you create, edit, or delete a custom user view, the changes will be shown in the **Filter** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="280c1-109">最大で 50 個のカスタム ビューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="280c1-109">You can create up to 50 custom views.</span></span> 

> [!TIP]
>  <span data-ttu-id="280c1-110">既定では、標準のユーザー ビューが [ **フィルター]** ドロップダウン リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="280c1-110">Standard user views are displayed by default in the **Filters** drop-down list.</span></span> <span data-ttu-id="280c1-111">標準フィルターには、すべてのユーザー 、ライセンスユーザー、ゲスト ユーザー 、サインイン許可、サインインが許可されている、ライセンスのないユーザー 、エラーのあるユーザー、課金管理者、グローバル管理者、**ヘルプ** デスク管理者、サービス管理者、およびユーザー管理管理者が含まれます。  </span><span class="sxs-lookup"><span data-stu-id="280c1-111">The standard filters include **All users**, **Licensed users**, **Guest users**,  **Sign-in allowed**, **Sign-in blocked**, **Unlicensed users**, **Users with errors**, **Billing admins**, **Global admins**, **Helpdesk admins**, **Service admins**, and **User management admins**.</span></span> <span data-ttu-id="280c1-112">標準ビューは編集または削除できません。</span><span class="sxs-lookup"><span data-stu-id="280c1-112">You can't edit or delete standard views.</span></span> 

<span data-ttu-id="280c1-113">標準ビューに関して次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="280c1-113">A few things to note about standard views:</span></span> 

- <span data-ttu-id="280c1-p104">一部の標準ビューでは、一覧のユーザー数が 2,000 を超えると、並べ替えられていない一覧が表示されます。このような一覧で特定のユーザーを探すには、検索ボックスを使います。</span><span class="sxs-lookup"><span data-stu-id="280c1-p104">Some standard views display an unsorted list if there are more than 2,000 users in the list. To locate specific users in this list, use the search box.</span></span> 
- <span data-ttu-id="280c1-116">Microsoft から Microsoft 365 を購入しなかった場合、課金管理者は標準ビューリストに表示されません。</span><span class="sxs-lookup"><span data-stu-id="280c1-116">If you didn't purchase Microsoft 365 from Microsoft, **Billing admins** don't appear in the standard views list.</span></span> <span data-ttu-id="280c1-117">詳細については、「[管理者ロールを割り当てる](assign-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="280c1-117">For more information, see [Assigning admin roles](assign-admin-roles.md).</span></span> 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a><span data-ttu-id="280c1-118">カスタム ユーザー ビューのフィルターを選択する</span><span class="sxs-lookup"><span data-stu-id="280c1-118">Choose the filters for your custom user view</span></span>

<span data-ttu-id="280c1-119">カスタム ビューは、[カスタム フィルター] ウィンドウ **で作成および編集** できます。</span><span class="sxs-lookup"><span data-stu-id="280c1-119">You can create and edit your custom views in the **Custom filter** pane.</span></span> <span data-ttu-id="280c1-120">複数のフィルター オプションを選択した場合は、選択したすべての条件に一致するユーザーを含む結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="280c1-120">If you select multiple filter options, you get results that contain users who match all the selected criteria.</span></span> <span data-ttu-id="280c1-121">次の例では、カナダにいる特定のドメイン上のすべてのユーザーを示す "Canadian users" (カナダのユーザー) という名前のカスタム ビューを作成する方法について示します。</span><span class="sxs-lookup"><span data-stu-id="280c1-121">The following example shows you how to create a custom view named "Canadian users" that shows all users on a specific domain who are in Canada.</span></span> 

  
 <span data-ttu-id="280c1-122">**A - ドメイン** 組織に複数のドメインがある場合は、使用可能なドメインのドロップダウン リストから選択できます。</span><span class="sxs-lookup"><span data-stu-id="280c1-122">**A - Domain** If you have multiple domains for your organization, you can choose from a drop-down list of domains that are available.</span></span> 
  
 <span data-ttu-id="280c1-123">**B - サインインの状態** 許可またはブロックされているユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="280c1-123">**B - Sign-in status** Choose users that are allowed or blocked.</span></span> 
  
 <span data-ttu-id="280c1-124">**C - 場所** 国のドロップダウン リストから場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="280c1-124">**C - Location** Choose a location from a drop-down list of countries.</span></span> 
  
 <span data-ttu-id="280c1-125">**D - 割り当てられた製品ライセンス** 組織で使用できるライセンスのドロップダウン リストから選択します。</span><span class="sxs-lookup"><span data-stu-id="280c1-125">**D - Assigned product license** Choose from a drop-down list of licenses that are available at your organization.</span></span> <span data-ttu-id="280c1-126">選択したライセンスが割り当てられているユーザーを表示するには、このフィルターを使います。</span><span class="sxs-lookup"><span data-stu-id="280c1-126">Use this filter to show users who have the license you selected assigned to them.</span></span> <span data-ttu-id="280c1-127">ユーザーは追加のライセンスを持っている場合もあります。</span><span class="sxs-lookup"><span data-stu-id="280c1-127">Users may also have additional licenses.</span></span> 
  
<span data-ttu-id="280c1-128">部門、市区町村、都道府県、国/地域、役職など、組織で使用される追加のユーザー プロファイルの詳細を使ってフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="280c1-128">You can also filter by additional user profile details used in your organization such as department, city, state or province, country or region, or job title.</span></span>
  
 <span data-ttu-id="280c1-129">**その他の条件:**</span><span class="sxs-lookup"><span data-stu-id="280c1-129">**Other conditions:**</span></span>
  
- <span data-ttu-id="280c1-130">**同期済みユーザーのみ** アクティブ化されているかどうかにかかわらず、ローカルの Active Directory と同期されているすべてのユーザーを表示するには、このボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="280c1-130">**Synchronized users only** Select this box to show all users who have been synced with the local Active Directory, regardless of whether the users have been activated or not.</span></span> 
    
- <span data-ttu-id="280c1-131">**エラーのあるユーザー** プロビジョニング エラーがある可能性のあるユーザーを表示するには、このボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="280c1-131">**Users with errors** Select this box to show users who may have provisioning errors.</span></span> 
    
- <span data-ttu-id="280c1-p108">**ライセンス未付与のユーザー** ライセンスが付与されていないすべてのユーザーを表示するには、このボックスをオンにします。このビューの結果には、Exchange メールボックスは持っていてもライセンスを持たないユーザーも含まれる場合があります。特にこのようなユーザーを追跡するには、[ **Exchange のメールボックスまたはアーカイブはあるがライセンスがないユーザー**] フィルターを使用します。このビューの結果には、Exchange アーカイブは持っていてもライセンスを持たないユーザーも含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="280c1-p108">**Unlicensed users** Select this box to find all the users who haven't been assigned a license. The results for this view can also include users who have an Exchange mailbox but don't have a license. To track those users specifically, use the filter **Unlicensed users with Exchange mailboxes or archives**. The results for this view can also include users who have an Exchange archive, but don't have a license.</span></span>
    
- <span data-ttu-id="280c1-136">**Exchange メールボックスまたはアーカイブを持つライセンスのないユーザー** Exchange Online で作成され、Exchange メールボックスを持っているが、Microsoft 365 ライセンスが割り当てられていないユーザー アカウントを表示するには、このボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="280c1-136">**Unlicensed users with Exchange mailboxes or archives** Select this box to show user accounts that were created in Exchange Online and have an Exchange mailbox, but weren't assigned an Microsoft 365 license.</span></span> <span data-ttu-id="280c1-137">このフィルターの結果には、Exchange アーカイブが割り当てられたユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="280c1-137">The results of this filter include users who have or who were assigned an Exchange archive.</span></span> 

> [!NOTE]
> <span data-ttu-id="280c1-138">**Exchange メールボックス フィルターを持つライセンスのないユーザー** は、次の場合に機能します。</span><span class="sxs-lookup"><span data-stu-id="280c1-138">The **Unlicensed users with Exchange mailboxes** filter works when:</span></span>
1. <span data-ttu-id="280c1-139">メールボックスは最近、共有からユーザー **に** 変換 **され** 、ライセンスはありません。</span><span class="sxs-lookup"><span data-stu-id="280c1-139">The mailbox has been recently converted from **shared** to **user** and it has no license.</span></span>
2. <span data-ttu-id="280c1-140">メールボックスは最近 Microsoft 365 に移行されましたが、ライセンスが割り当てられていない。</span><span class="sxs-lookup"><span data-stu-id="280c1-140">The mailbox has been recently migrated to Microsoft 365 but a license has not been assigned.</span></span>
3. <span data-ttu-id="280c1-141">PowerShell を使用してメールボックスが作成され、ライセンスが割り当てられていない。</span><span class="sxs-lookup"><span data-stu-id="280c1-141">The mailbox has been created using PowerShell, and a license has not been assigned.</span></span>
4. <span data-ttu-id="280c1-142">ユーザーのコマンドレットを使用してオンプレミスで作成New-RemoteMailboxメールボックスが準備されます。</span><span class="sxs-lookup"><span data-stu-id="280c1-142">A new mailbox that has been created on-premise with a New-RemoteMailbox cmdlet is provisioned for the user.</span></span>
    
> [!TIP]
> <span data-ttu-id="280c1-143">2,000 を超えるユーザーを返すカスタム ビューを作成すると、結果のユーザー一覧は並べ替えられません。</span><span class="sxs-lookup"><span data-stu-id="280c1-143">If you create a custom view that returns more than 2,000 users, the resulting user list isn't sorted.</span></span> <span data-ttu-id="280c1-144">この場合は、検索ボックスを使用してユーザーを検索するか、カスタム ビューを編集して検索を絞り込めます。</span><span class="sxs-lookup"><span data-stu-id="280c1-144">In this case, use the search box to find users or edit your custom view to refine your search.</span></span> 
  
## <a name="create-a-custom-user-view"></a><span data-ttu-id="280c1-145">カスタム ユーザー ビューの作成</span><span class="sxs-lookup"><span data-stu-id="280c1-145">Create a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="280c1-146">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="280c1-146">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.</span></span>
    
2. <span data-ttu-id="280c1-147">[アクティブ な **ユーザー] ページで** 、[フィルター] **を選択し** 、[新しいフィルター **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="280c1-147">On the **Active users** page, select **Filters** and select **New filter**.</span></span>
  
3. <span data-ttu-id="280c1-148">[カスタム フィルター **] ページ** で、フィルターの名前を入力し、カスタム フィルターの条件を選択し、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="280c1-148">On the **Custom filter** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="280c1-149">これで、カスタム ビューがフィルターのドロップダウン リストに含まれます。</span><span class="sxs-lookup"><span data-stu-id="280c1-149">Your custom view is now included in the drop-down list of filters.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="280c1-150">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="280c1-150">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.</span></span>  

2. <span data-ttu-id="280c1-151">[アクティブ な **ユーザー] ページで** 、[ビュー] **を選択し** 、[カスタム **ビューの追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="280c1-151">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="280c1-152">[カスタム ビュー **] ページ** で、フィルターの名前を入力し、カスタム フィルターの条件を選択し、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="280c1-152">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="280c1-153">これで、カスタム ビューがフィルターのドロップダウン リストに含まれます。</span><span class="sxs-lookup"><span data-stu-id="280c1-153">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end


::: moniker range="o365-21vianet"

1. <span data-ttu-id="280c1-154">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="280c1-154">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>.</span></span> 

2. <span data-ttu-id="280c1-155">[アクティブ な **ユーザー] ページで** 、[ビュー] **を選択し** 、[カスタム **ビューの追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="280c1-155">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="280c1-156">[カスタム ビュー **] ページ** で、フィルターの名前を入力し、カスタム フィルターの条件を選択し、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="280c1-156">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="280c1-157">これで、カスタム ビューがフィルターのドロップダウン リストに含まれます。</span><span class="sxs-lookup"><span data-stu-id="280c1-157">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a><span data-ttu-id="280c1-158">カスタム ユーザー ビューの編集または削除</span><span class="sxs-lookup"><span data-stu-id="280c1-158">Edit or delete a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="280c1-159">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="280c1-159">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.</span></span>
    
2. <span data-ttu-id="280c1-160">[アクティブ な **ユーザー] ページで** 、[ **フィルター**] を選択し、変更するフィルターを選択し、[フィルターの編集] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="280c1-160">On the **Active users** page, select **Filter**, select the filter you want to change, and then select **Edit filter**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="280c1-161">編集できるのはカスタム ビューだけです。</span><span class="sxs-lookup"><span data-stu-id="280c1-161">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="280c1-162">[カスタム フィルター **] ページで** 、必要に応じて情報を編集し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="280c1-162">On the **Custom filter** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="280c1-163">または、フィルターを削除するには、ページの下部にある [削除] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="280c1-163">Or, to delete the filter, at the bottom of the page select **Delete**.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="280c1-164">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="280c1-164">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.</span></span>  

2. <span data-ttu-id="280c1-165">[アクティブ な **ユーザー] ページで** 、[ **ビュー]** を選択し、変更するフィルターを選択し、[このビューの編集 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="280c1-165">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="280c1-166">編集できるのはカスタム ビューだけです。</span><span class="sxs-lookup"><span data-stu-id="280c1-166">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="280c1-167">[カスタム ビュー **] ページで** 、必要に応じて情報を編集し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="280c1-167">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="280c1-168">または、フィルターを削除するには、ページの下部にある [カスタム ビューの削除 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="280c1-168">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="280c1-169">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="280c1-169">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>.</span></span> 

2. <span data-ttu-id="280c1-170">[アクティブ な **ユーザー] ページで** 、[ **ビュー]** を選択し、変更するフィルターを選択し、[このビューの編集 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="280c1-170">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="280c1-171">編集できるのはカスタム ビューだけです。</span><span class="sxs-lookup"><span data-stu-id="280c1-171">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="280c1-172">[カスタム ビュー **] ページで** 、必要に応じて情報を編集し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="280c1-172">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="280c1-173">または、フィルターを削除するには、ページの下部にある [カスタム ビューの削除 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="280c1-173">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end


     