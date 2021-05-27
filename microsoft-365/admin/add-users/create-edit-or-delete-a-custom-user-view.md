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
description: フィルターを使用してカスタム ユーザー ビューを作成、編集、または削除する方法については、Microsoft 365。
ms.openlocfilehash: b4177a561d13d76f6d5a0a1077fe8037d469ee48
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683225"
---
# <a name="create-edit-or-delete-a-custom-user-view"></a><span data-ttu-id="846f6-103">カスタム ユーザー ビューを作成、編集、削除する</span><span class="sxs-lookup"><span data-stu-id="846f6-103">Create, edit, or delete a custom user view</span></span>

<span data-ttu-id="846f6-104">ビジネス サブスクリプションの Microsoft 365 またはユーザー管理管理者の場合は、カスタム ユーザー ビューを作成して、ユーザーの特定のサブセットを表示できます。</span><span class="sxs-lookup"><span data-stu-id="846f6-104">If you're a global or user management admin of a Microsoft 365 for business subscription,  you can create custom user views to view a specific subset of users.</span></span> <span data-ttu-id="846f6-105">これらのビューは、標準のビューセットに加えて表示されます。</span><span class="sxs-lookup"><span data-stu-id="846f6-105">These views are in addition to the standard set of views.</span></span> <span data-ttu-id="846f6-106">カスタム ユーザー ビューは作成、編集、削除でき、ある管理者が作成したカスタム ビューはすべての管理者が使用できます。</span><span class="sxs-lookup"><span data-stu-id="846f6-106">You can create, edit, or delete custom user views, and the custom views you create are available to all admins.</span></span>
  
## <a name="custom-user-views-in-the-admin-center"></a><span data-ttu-id="846f6-107">管理センターのカスタム ユーザー ビュー</span><span class="sxs-lookup"><span data-stu-id="846f6-107">Custom user views in the admin center</span></span>

<span data-ttu-id="846f6-108">カスタム ユーザー ビューを作成、編集、または削除すると、変更が [ユーザー]ページに移動すると、会社のすべての管理者が表示するフィルター リスト **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="846f6-108">When you create, edit, or delete a custom user view, the changes will be shown in the **Filter** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="846f6-109">最大で 50 個のカスタム ビューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="846f6-109">You can create up to 50 custom views.</span></span> 

> [!TIP]
>  <span data-ttu-id="846f6-110">既定では、標準のユーザー ビューが [ **フィルター]** ドロップダウン リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="846f6-110">Standard user views are displayed by default in the **Filters** drop-down list.</span></span> <span data-ttu-id="846f6-111">標準フィルターには、すべてのユーザー 、ライセンスユーザー、ゲスト ユーザー 、サインイン許可、サインインが許可されている、ライセンスのないユーザー 、エラーのあるユーザー、課金管理者、グローバル管理者、**ヘルプ** デスク管理者、サービス管理者、およびユーザー管理管理者が含まれます。  </span><span class="sxs-lookup"><span data-stu-id="846f6-111">The standard filters include **All users**, **Licensed users**, **Guest users**,  **Sign-in allowed**, **Sign-in blocked**, **Unlicensed users**, **Users with errors**, **Billing admins**, **Global admins**, **Helpdesk admins**, **Service admins**, and **User management admins**.</span></span> <span data-ttu-id="846f6-112">標準ビューは編集または削除できません。</span><span class="sxs-lookup"><span data-stu-id="846f6-112">You can't edit or delete standard views.</span></span> 

<span data-ttu-id="846f6-113">標準ビューに関して次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="846f6-113">A few things to note about standard views:</span></span> 

- <span data-ttu-id="846f6-p104">一部の標準ビューでは、一覧のユーザー数が 2,000 を超えると、並べ替えられていない一覧が表示されます。このような一覧で特定のユーザーを探すには、検索ボックスを使います。</span><span class="sxs-lookup"><span data-stu-id="846f6-p104">Some standard views display an unsorted list if there are more than 2,000 users in the list. To locate specific users in this list, use the search box.</span></span> 
- <span data-ttu-id="846f6-116">Microsoft からアプリを購入しなかったMicrosoft 365、**課金** 管理者は標準ビューの一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="846f6-116">If you didn't purchase Microsoft 365 from Microsoft, **Billing admins** don't appear in the standard views list.</span></span> <span data-ttu-id="846f6-117">詳細については、「[管理者ロールを割り当てる](assign-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="846f6-117">For more information, see [Assigning admin roles](assign-admin-roles.md).</span></span> 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a><span data-ttu-id="846f6-118">カスタム ユーザー ビューのフィルターを選択する</span><span class="sxs-lookup"><span data-stu-id="846f6-118">Choose the filters for your custom user view</span></span>

<span data-ttu-id="846f6-119">カスタム ビューは、[カスタム フィルター] ウィンドウ **で作成および編集** できます。</span><span class="sxs-lookup"><span data-stu-id="846f6-119">You can create and edit your custom views in the **Custom filter** pane.</span></span> <span data-ttu-id="846f6-120">複数のフィルター オプションを選択した場合は、選択したすべての条件に一致するユーザーを含む結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="846f6-120">If you select multiple filter options, you get results that contain users who match all the selected criteria.</span></span> <span data-ttu-id="846f6-121">次の例では、カナダにいる特定のドメイン上のすべてのユーザーを示す "Canadian users" (カナダのユーザー) という名前のカスタム ビューを作成する方法について示します。</span><span class="sxs-lookup"><span data-stu-id="846f6-121">The following example shows you how to create a custom view named "Canadian users" that shows all users on a specific domain who are in Canada.</span></span> 

  
 <span data-ttu-id="846f6-122">**A - ドメイン** 組織に複数のドメインがある場合は、使用可能なドメインのドロップダウン リストから選択できます。</span><span class="sxs-lookup"><span data-stu-id="846f6-122">**A - Domain** If you have multiple domains for your organization, you can choose from a drop-down list of domains that are available.</span></span> 
  
 <span data-ttu-id="846f6-123">**B - サインインの状態** 許可またはブロックされているユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="846f6-123">**B - Sign-in status** Choose users that are allowed or blocked.</span></span> 
  
 <span data-ttu-id="846f6-124">**C - 場所** 国のドロップダウン リストから場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="846f6-124">**C - Location** Choose a location from a drop-down list of countries.</span></span> 
  
 <span data-ttu-id="846f6-125">**D - 割り当てられた製品ライセンス** 組織で使用できるライセンスのドロップダウン リストから選択します。</span><span class="sxs-lookup"><span data-stu-id="846f6-125">**D - Assigned product license** Choose from a drop-down list of licenses that are available at your organization.</span></span> <span data-ttu-id="846f6-126">選択したライセンスが割り当てられているユーザーを表示するには、このフィルターを使います。</span><span class="sxs-lookup"><span data-stu-id="846f6-126">Use this filter to show users who have the license you selected assigned to them.</span></span> <span data-ttu-id="846f6-127">ユーザーは追加のライセンスを持っている場合もあります。</span><span class="sxs-lookup"><span data-stu-id="846f6-127">Users may also have additional licenses.</span></span> 
  
<span data-ttu-id="846f6-128">部門、市区町村、都道府県、国/地域、役職など、組織で使用される追加のユーザー プロファイルの詳細を使ってフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="846f6-128">You can also filter by additional user profile details used in your organization such as department, city, state or province, country or region, or job title.</span></span>
  
 <span data-ttu-id="846f6-129">**その他の条件:**</span><span class="sxs-lookup"><span data-stu-id="846f6-129">**Other conditions:**</span></span>
  
- <span data-ttu-id="846f6-130">**同期済みユーザーのみ** アクティブ化されているかどうかにかかわらず、ローカルの Active Directory と同期されているすべてのユーザーを表示するには、このボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="846f6-130">**Synchronized users only** Select this box to show all users who have been synced with the local Active Directory, regardless of whether the users have been activated or not.</span></span> 
    
- <span data-ttu-id="846f6-131">**エラーのあるユーザー** プロビジョニング エラーがある可能性のあるユーザーを表示するには、このボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="846f6-131">**Users with errors** Select this box to show users who may have provisioning errors.</span></span> 
    
- <span data-ttu-id="846f6-p108">**ライセンス未付与のユーザー** ライセンスが付与されていないすべてのユーザーを表示するには、このボックスをオンにします。このビューの結果には、Exchange メールボックスは持っていてもライセンスを持たないユーザーも含まれる場合があります。特にこのようなユーザーを追跡するには、[ **Exchange のメールボックスまたはアーカイブはあるがライセンスがないユーザー**] フィルターを使用します。このビューの結果には、Exchange アーカイブは持っていてもライセンスを持たないユーザーも含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="846f6-p108">**Unlicensed users** Select this box to find all the users who haven't been assigned a license. The results for this view can also include users who have an Exchange mailbox but don't have a license. To track those users specifically, use the filter **Unlicensed users with Exchange mailboxes or archives**. The results for this view can also include users who have an Exchange archive, but don't have a license.</span></span>
    
- <span data-ttu-id="846f6-136">**ユーザーのメールボックスまたはアーカイブExchangeライセンスのないユーザー** このボックスを選択すると、Exchange Online で作成され、Exchange メールボックスが割り当てられていないユーザー アカウントMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="846f6-136">**Unlicensed users with Exchange mailboxes or archives** Select this box to show user accounts that were created in Exchange Online and have an Exchange mailbox, but weren't assigned an Microsoft 365 license.</span></span> <span data-ttu-id="846f6-137">このフィルターの結果には、Exchange アーカイブが割り当てられたユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="846f6-137">The results of this filter include users who have or who were assigned an Exchange archive.</span></span> 

> [!NOTE]
> <span data-ttu-id="846f6-138">次 **の場合に、メールボックス** フィルター Exchangeライセンスのないユーザーが機能します。</span><span class="sxs-lookup"><span data-stu-id="846f6-138">The **Unlicensed users with Exchange mailboxes** filter works when:</span></span>
1. <span data-ttu-id="846f6-139">メールボックスは最近、共有からユーザー **に** 変換 **され** 、ライセンスはありません。</span><span class="sxs-lookup"><span data-stu-id="846f6-139">The mailbox has been recently converted from **shared** to **user** and it has no license.</span></span>
2. <span data-ttu-id="846f6-140">メールボックスは最近、ユーザーに移行Microsoft 365ライセンスが割り当てられていない。</span><span class="sxs-lookup"><span data-stu-id="846f6-140">The mailbox has been recently migrated to Microsoft 365 but a license has not been assigned.</span></span>
3. <span data-ttu-id="846f6-141">PowerShell を使用してメールボックスが作成され、ライセンスが割り当てられていない。</span><span class="sxs-lookup"><span data-stu-id="846f6-141">The mailbox has been created using PowerShell, and a license has not been assigned.</span></span>
4. <span data-ttu-id="846f6-142">ユーザーのコマンドレットを使用してオンプレミスで作成New-RemoteMailboxメールボックスが準備されます。</span><span class="sxs-lookup"><span data-stu-id="846f6-142">A new mailbox that has been created on-premise with a New-RemoteMailbox cmdlet is provisioned for the user.</span></span>
    
> [!TIP]
> <span data-ttu-id="846f6-143">2,000 を超えるユーザーを返すカスタム ビューを作成すると、結果のユーザー一覧は並べ替えられません。</span><span class="sxs-lookup"><span data-stu-id="846f6-143">If you create a custom view that returns more than 2,000 users, the resulting user list isn't sorted.</span></span> <span data-ttu-id="846f6-144">この場合は、検索ボックスを使用してユーザーを検索するか、カスタム ビューを編集して検索を絞り込めます。</span><span class="sxs-lookup"><span data-stu-id="846f6-144">In this case, use the search box to find users or edit your custom view to refine your search.</span></span> 
  
## <a name="create-a-custom-user-view"></a><span data-ttu-id="846f6-145">カスタム ユーザー ビューの作成</span><span class="sxs-lookup"><span data-stu-id="846f6-145">Create a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="846f6-146">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="846f6-146">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="846f6-147">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="846f6-147">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="846f6-148">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="846f6-148">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>.</span></span>  

::: moniker-end
    
2. <span data-ttu-id="846f6-149">[アクティブ な **ユーザー] ページで** 、[フィルター] **を選択し** 、[新しいフィルター **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="846f6-149">On the **Active users** page, select **Filters** and select **New filter**.</span></span>
  
3. <span data-ttu-id="846f6-150">[カスタム フィルター **] ページ** で、フィルターの名前を入力し、カスタム フィルターの条件を選択し、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="846f6-150">On the **Custom filter** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="846f6-151">これで、カスタム ビューがフィルターのドロップダウン リストに含まれます。</span><span class="sxs-lookup"><span data-stu-id="846f6-151">Your custom view is now included in the drop-down list of filters.</span></span>

## <a name="edit-or-delete-a-custom-user-view"></a><span data-ttu-id="846f6-152">カスタム ユーザー ビューの編集または削除</span><span class="sxs-lookup"><span data-stu-id="846f6-152">Edit or delete a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="846f6-153">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="846f6-153">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="846f6-154">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="846f6-154">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="846f6-155">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="846f6-155">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>.</span></span> 

::: moniker-end 
    
2. <span data-ttu-id="846f6-156">[アクティブ な **ユーザー] ページで** 、[ **フィルター**] を選択し、変更するフィルターを選択し、[フィルターの編集] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="846f6-156">On the **Active users** page, select **Filter**, select the filter you want to change, and then select **Edit filter**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="846f6-157">編集できるのはカスタム ビューだけです。</span><span class="sxs-lookup"><span data-stu-id="846f6-157">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="846f6-158">[カスタム フィルター **] ページで** 、必要に応じて情報を編集し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="846f6-158">On the **Custom filter** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="846f6-159">または、フィルターを削除するには、ページの下部にある [削除] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="846f6-159">Or, to delete the filter, at the bottom of the page select **Delete**.</span></span> 

## <a name="related-content"></a><span data-ttu-id="846f6-160">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="846f6-160">Related content</span></span>

<span data-ttu-id="846f6-161">[管理センター Microsoft 365の概要](../../business-video/admin-center-overview.md)(ビデオ)</span><span class="sxs-lookup"><span data-stu-id="846f6-161">[Overview of the Microsoft 365 admin center](../../business-video/admin-center-overview.md) (video)</span></span>\
<span data-ttu-id="846f6-162">[管理者の役割](../add-users/about-admin-roles.md) (ビデオ)</span><span class="sxs-lookup"><span data-stu-id="846f6-162">[About admin roles](../add-users/about-admin-roles.md) (video)</span></span>\
<span data-ttu-id="846f6-163">[組織のMicrosoft 365テーマをカスタマイズする](../setup/customize-your-organization-theme.md)(記事)</span><span class="sxs-lookup"><span data-stu-id="846f6-163">[Customize the Microsoft 365 theme for your organization](../setup/customize-your-organization-theme.md) (article)</span></span>


     