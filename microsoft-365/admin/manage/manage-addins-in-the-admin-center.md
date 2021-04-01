---
title: 管理センターでアドインを管理する
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
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 集中型アドインを使用して組織内のユーザーとグループにアドインを展開する方法について学習します。
ms.openlocfilehash: 836dfa7a0c1b6cf1550e5c139bc0ca36be8f5424
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470943"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="73793-103">管理センターでアドインを管理する</span><span class="sxs-lookup"><span data-stu-id="73793-103">Manage add-ins in the admin center</span></span>

<span data-ttu-id="73793-104">Officeアドインを使用すると、ドキュメントをカスタマイズし、Web 上の情報にアクセスする方法を合理化できます (「Office アドインの使用を開始する」を [参照してください](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862))。</span><span class="sxs-lookup"><span data-stu-id="73793-104">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="73793-105">管理者が組織内のユーザーにアドインを展開した後、管理者はアドインをオフまたはオン、編集、削除、およびアドインへのアクセスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="73793-105">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="73793-106">管理センターからのアドインのインストールの詳細については、「管理センターでアドインを展開する」 [を参照してください](./manage-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="73793-106">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="73793-107">アドインの状態</span><span class="sxs-lookup"><span data-stu-id="73793-107">Add-in states</span></span>

<span data-ttu-id="73793-108">アドインは[オン]または **[オフ]** のいずれかの状態 **にできます** 。</span><span class="sxs-lookup"><span data-stu-id="73793-108">An add-in can be in either the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="73793-109">**状態**</span><span class="sxs-lookup"><span data-stu-id="73793-109">**State**</span></span>|<span data-ttu-id="73793-110">**状態が発生する原因**</span><span class="sxs-lookup"><span data-stu-id="73793-110">**How the state occurs**</span></span>|<span data-ttu-id="73793-111">**影響**</span><span class="sxs-lookup"><span data-stu-id="73793-111">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="73793-112">**Active**</span><span class="sxs-lookup"><span data-stu-id="73793-112">**Active**</span></span>  <br/> |<span data-ttu-id="73793-113">管理者はアドインをアップロードし、ユーザーまたはグループに割り当てしました。</span><span class="sxs-lookup"><span data-stu-id="73793-113">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="73793-114">アドインを割り当てられたユーザーやグループは、関連するクライアントでアドインを表示します。</span><span class="sxs-lookup"><span data-stu-id="73793-114">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="73793-115">**オフ**</span><span class="sxs-lookup"><span data-stu-id="73793-115">**Turned off**</span></span>  <br/> |<span data-ttu-id="73793-116">管理者がアドインをオフにした。</span><span class="sxs-lookup"><span data-stu-id="73793-116">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="73793-117">アドインを割り当てられたユーザーやグループは、そのアドインにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="73793-117">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="73793-118">アドインの状態が [アクティブ] に変更されると、ユーザーやグループはもう一度アクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="73793-118">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="73793-119">**Deleted**</span><span class="sxs-lookup"><span data-stu-id="73793-119">**Deleted**</span></span>  <br/> |<span data-ttu-id="73793-120">管理者がアドインを削除した。</span><span class="sxs-lookup"><span data-stu-id="73793-120">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="73793-121">アドインを割り当てられたユーザーやグループは、そのアドインにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="73793-121">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="73793-122">アドインを使用しているユーザーがいない場合は、削除を検討してください。</span><span class="sxs-lookup"><span data-stu-id="73793-122">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="73793-123">たとえば、一年の特定の期間中にのみアドインを使用する場合は、アドインをオフにしてください。</span><span class="sxs-lookup"><span data-stu-id="73793-123">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="73793-124">アドインを削除する</span><span class="sxs-lookup"><span data-stu-id="73793-124">Delete an add-in</span></span>

<span data-ttu-id="73793-125">展開されたアドインを削除できます。</span><span class="sxs-lookup"><span data-stu-id="73793-125">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="73793-126">管理センターで、[アドイン **の設定**  >  **サービス] &に移動** します。</span><span class="sxs-lookup"><span data-stu-id="73793-126">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="73793-127">管理センターは、統合アプリを使用した展開エクスペリエンスに更新されています。</span><span class="sxs-lookup"><span data-stu-id="73793-127">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="73793-128">上記の手順が表示されない場合は、[設定] 統合アプリに移動して、[集中展開]  >  **セクションに移動します**。</span><span class="sxs-lookup"><span data-stu-id="73793-128">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="73793-129">[統合アプリ] ページ **の上部** で、[アドイン] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="73793-129">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="73793-130">展開されたアドインを選択します。</span><span class="sxs-lookup"><span data-stu-id="73793-130">Select the deployed add-in.</span></span>

3. <span data-ttu-id="73793-131">[アドインの **削除] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="73793-131">Click on **Delete Add-In**.</span></span> <span data-ttu-id="73793-132">右下隅にある [アドイン] ボタンを削除します。</span><span class="sxs-lookup"><span data-stu-id="73793-132">Remove the Add-in button on the bottom right corner.</span></span>

4. <span data-ttu-id="73793-133">選択内容を確認し、[**アドインの削除]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="73793-133">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="73793-134">アドインのアクセスを編集する</span><span class="sxs-lookup"><span data-stu-id="73793-134">Edit add-in access</span></span>

<span data-ttu-id="73793-135">展開後、管理者はアドインへのユーザー アクセスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="73793-135">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="73793-136">管理センターで、[アドイン **の設定**  >  **サービス] &に移動** します。</span><span class="sxs-lookup"><span data-stu-id="73793-136">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="73793-137">管理センターは、統合アプリを使用した展開エクスペリエンスに更新されています。</span><span class="sxs-lookup"><span data-stu-id="73793-137">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="73793-138">上記の手順が表示されない場合は、[設定] 統合アプリに移動して、[集中展開]  >  **セクションに移動します**。</span><span class="sxs-lookup"><span data-stu-id="73793-138">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="73793-139">[統合アプリ] ページ **の上部** で、[アドイン] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="73793-139">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="73793-140">展開されたアドインを選択します。</span><span class="sxs-lookup"><span data-stu-id="73793-140">Select the deployed add-in.</span></span>

3. <span data-ttu-id="73793-141">[アクセス権を **持つユーザー]** **の下の [編集] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="73793-141">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="73793-142">変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="73793-142">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="73793-143">すべてのクライアントでアドイン ストアをオフにしてアドインOfficeを防止する (Outlook を除く)</span><span class="sxs-lookup"><span data-stu-id="73793-143">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="73793-144">Outlook アドインのインストールは、別のプロセスによって [管理されます](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="73793-144">Outlook add-in installation is managed by a [different process](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins).</span></span>

<span data-ttu-id="73793-145">組織として、新しいアドインを OfficeストアからダウンロードOfficeがあります。</span><span class="sxs-lookup"><span data-stu-id="73793-145">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="73793-146">これを集中展開と組み合わせて使用して、組織で承認されたアドインのみを組織内のユーザーに展開できます。</span><span class="sxs-lookup"><span data-stu-id="73793-146">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="73793-147">**アドインの取得をオフにする**</span><span class="sxs-lookup"><span data-stu-id="73793-147">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="73793-148">管理センターで、 [**設定**] \> [[サービス&amp;アドイン](https://go.microsoft.com/fwlink/p/?linkid=2053743)] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="73793-148">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="73793-149">管理センターは、統合アプリを使用した展開エクスペリエンスに更新されています。</span><span class="sxs-lookup"><span data-stu-id="73793-149">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="73793-150">上記の手順が表示されない場合は、[設定] 統合アプリに移動して、[集中展開]  >  **セクションに移動します**。</span><span class="sxs-lookup"><span data-stu-id="73793-150">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="73793-151">[統合アプリ] ページ **の上部** で、[アドイン] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="73793-151">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="73793-152">**[ユーザー所有のアプリとサービス]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="73793-152">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="73793-153">ユーザーが Office ストアにアクセスできるようにするオプションをオフにします。</span><span class="sxs-lookup"><span data-stu-id="73793-153">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="73793-154">これにより、すべてのユーザーがストアから次のアドインを取得できます。</span><span class="sxs-lookup"><span data-stu-id="73793-154">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="73793-155">Word、Excel、および PowerPoint 2016 のアドインは、次の場所から使用できます。</span><span class="sxs-lookup"><span data-stu-id="73793-155">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="73793-156">Windows</span><span class="sxs-lookup"><span data-stu-id="73793-156">Windows</span></span>
    
  - <span data-ttu-id="73793-157">Mac</span><span class="sxs-lookup"><span data-stu-id="73793-157">Mac</span></span>
    
  - <span data-ttu-id="73793-158">Office</span><span class="sxs-lookup"><span data-stu-id="73793-158">Office</span></span>
    
    
- <span data-ttu-id="73793-159">AppSource 内から **始まる取得**</span><span class="sxs-lookup"><span data-stu-id="73793-159">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="73793-160">Microsoft 365 内のアドイン</span><span class="sxs-lookup"><span data-stu-id="73793-160">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="73793-161">ストアにアクセスしようとすると、次のメッセージが表示されます。申し訳ありませんが **、Microsoft 365** は、Office ストア アドインの個別の取得を防止するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="73793-161">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="73793-162">ストアをオフにOfficeサポートは、次のバージョンで使用できます。</span><span class="sxs-lookup"><span data-stu-id="73793-162">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="73793-163">Windows: 16.0.9001 - 現在利用可能です。</span><span class="sxs-lookup"><span data-stu-id="73793-163">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="73793-164">Mac: 16.10.18011401 - 現在利用可能です。</span><span class="sxs-lookup"><span data-stu-id="73793-164">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="73793-165">iOS: 2.9.18010804 - 現在利用可能です。</span><span class="sxs-lookup"><span data-stu-id="73793-165">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="73793-166">Web - 現在利用可能です。</span><span class="sxs-lookup"><span data-stu-id="73793-166">The web - Currently available.</span></span>
    
<span data-ttu-id="73793-167">これにより、管理者が一元展開を使用してアドインを管理ストアから割り当Officeされません。</span><span class="sxs-lookup"><span data-stu-id="73793-167">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="73793-168">ユーザーが Microsoft アカウントでサインインを防止するには、組織アカウントのみを使用するログオンを制限できます。</span><span class="sxs-lookup"><span data-stu-id="73793-168">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="73793-169">詳細については [、2016 年の ID、](/DeployOffice/security/identity-authentication-and-authorization-in-office)認証、および認証Office参照してください。</span><span class="sxs-lookup"><span data-stu-id="73793-169">For more information, see [Identity, authentication, and authorization in Office 2016](/DeployOffice/security/identity-authentication-and-authorization-in-office).</span></span>  

> [!NOTE]
> <span data-ttu-id="73793-170">ユーザーが Office ストアにアクセスしなかOfficeアドインをサイドローディング [してテストを行うのも妨げる可能性があります](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="73793-170">Preventing users from accessing the office store will also prevent them from [Sideloading Office Add-ins for testing](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span></span>

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="73793-171">アドインを使用したエンド ユーザー エクスペリエンスの詳細</span><span class="sxs-lookup"><span data-stu-id="73793-171">More about the end user experience with add-ins</span></span>

<span data-ttu-id="73793-172">アドインを展開すると、エンド ユーザーはアドインを Office アプリケーションで使用できます (「アドインの使用を開始する [Office」を参照してください](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862))。</span><span class="sxs-lookup"><span data-stu-id="73793-172">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="73793-173">アドインは、アドインがサポートしているすべてのプラットフォームに表示されます。</span><span class="sxs-lookup"><span data-stu-id="73793-173">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="73793-p109">アドインがアドイン コマンドをサポートする場合、そのコマンドは Office のリボンに表示されます。次の例では、[ **引用の検索** ] コマンドが [ **引用** ] アドインで表示されています。</span><span class="sxs-lookup"><span data-stu-id="73793-p109">If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Office付きリボン](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="73793-177">展開されたアドインがアドイン コマンドをサポートしない場合、またはすべての展開されたアドインを表示する場合は、[マイ アドイン] を使用して表示 **できます**。</span><span class="sxs-lookup"><span data-stu-id="73793-177">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="73793-178">Word 2016、Excel 2016、または PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="73793-178">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="73793-179">[ **アドイン \> の挿入] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="73793-179">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="73793-180">Office アドイン ウィンドウの [ **管理による管理者** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="73793-180">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="73793-181">前に展開したアドインをダブルクリックします (この例では [ **引用文献** ])。</span><span class="sxs-lookup"><span data-stu-id="73793-181">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="73793-182">![[アドイン] ページの [Office管理] タブ](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="73793-182">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="73793-183">Outlook</span><span class="sxs-lookup"><span data-stu-id="73793-183">In Outlook</span></span>

1. <span data-ttu-id="73793-184">[ホーム **] リボンで** 、[ **アドインの取得] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="73793-184">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="73793-185">![Outlook の [格納] ボタン](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="73793-185">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="73793-186">左側のナビゲーションで、**[管理者が管理]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="73793-186">Select **Admin-managed** in the left nav.</span></span> 

## <a name="learn-more"></a><span data-ttu-id="73793-187">詳細情報</span><span class="sxs-lookup"><span data-stu-id="73793-187">Learn more</span></span>

[<span data-ttu-id="73793-188">管理センターでアドインを展開する</span><span class="sxs-lookup"><span data-stu-id="73793-188">Deploy add-ins in the admin center</span></span>](./manage-deployment-of-add-ins.md)

<span data-ttu-id="73793-189">[Office アドイン](/office/dev/add-ins/overview/office-add-ins)の作成と構築の詳細情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="73793-189">Learn more about creating and building [Office Add-ins](/office/dev/add-ins/overview/office-add-ins).</span></span>
  
<span data-ttu-id="73793-190">[アドインを管理するには、集中展開 PowerShell コマンドレットを使用します](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="73793-190">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md).</span></span>
  
[<span data-ttu-id="73793-191">トラブルシューティング: アドインが表示されないユーザー</span><span class="sxs-lookup"><span data-stu-id="73793-191">Troubleshoot: User not seeing add-ins</span></span>](/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[<span data-ttu-id="73793-192">未成年者と Microsoft Store からアドインを取得する</span><span class="sxs-lookup"><span data-stu-id="73793-192">Minors and acquiring add-ins from the Microsoft Store</span></span>](./minors-and-acquiring-addins-from-the-store.md)