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
description: 一元化されたアドインを使用して、組織内のユーザーとグループにアドインを展開する方法について学習します。
ms.openlocfilehash: 5366bd5be80559f23490aeb54f9417a189169e12
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114203"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="4c666-103">管理センターでアドインを管理する</span><span class="sxs-lookup"><span data-stu-id="4c666-103">Manage add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="4c666-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="4c666-104">The admin center is changing.</span></span> <span data-ttu-id="4c666-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c666-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="4c666-106">Officeアドインを使用すると、ドキュメントをカスタマイズし、Web 上の情報にアクセスする方法を効率化できます (「Office アドインの使用を開始する」を参照 [してください](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862))。</span><span class="sxs-lookup"><span data-stu-id="4c666-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="4c666-107">管理者が組織内のユーザー用のアドインを展開した後、管理者はアドインのオフまたはオン、編集、削除、およびアドインへのアクセスの管理を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="4c666-107">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="4c666-108">管理センターからのアドインのインストールの詳細については、「管理センターでアドインを展開する」 [を参照してください](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="4c666-108">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="4c666-109">アドインの状態</span><span class="sxs-lookup"><span data-stu-id="4c666-109">Add-in states</span></span>

<span data-ttu-id="4c666-110">アドインは、オンまたはオフのいずれかの **状態** に **できます** 。</span><span class="sxs-lookup"><span data-stu-id="4c666-110">An add-in can be in either the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="4c666-111">**状態**</span><span class="sxs-lookup"><span data-stu-id="4c666-111">**State**</span></span>|<span data-ttu-id="4c666-112">**状態が発生する原因**</span><span class="sxs-lookup"><span data-stu-id="4c666-112">**How the state occurs**</span></span>|<span data-ttu-id="4c666-113">**影響**</span><span class="sxs-lookup"><span data-stu-id="4c666-113">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4c666-114">**Active**</span><span class="sxs-lookup"><span data-stu-id="4c666-114">**Active**</span></span>  <br/> |<span data-ttu-id="4c666-115">管理者がアドインをアップロードし、ユーザーまたはグループに割り当てた。</span><span class="sxs-lookup"><span data-stu-id="4c666-115">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="4c666-116">アドインを割り当てられたユーザーやグループは、関連するクライアントでアドインを表示します。</span><span class="sxs-lookup"><span data-stu-id="4c666-116">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="4c666-117">**オフ**</span><span class="sxs-lookup"><span data-stu-id="4c666-117">**Turned off**</span></span>  <br/> |<span data-ttu-id="4c666-118">管理者がアドインをオフにした。</span><span class="sxs-lookup"><span data-stu-id="4c666-118">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="4c666-119">アドインを割り当てられたユーザーやグループは、そのアドインにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="4c666-119">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="4c666-120">アドインの状態が [アクティブ] に変更されると、ユーザーやグループはもう一度アクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="4c666-120">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="4c666-121">**Deleted**</span><span class="sxs-lookup"><span data-stu-id="4c666-121">**Deleted**</span></span>  <br/> |<span data-ttu-id="4c666-122">管理者がアドインを削除した。</span><span class="sxs-lookup"><span data-stu-id="4c666-122">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="4c666-123">アドインを割り当てられたユーザーやグループは、そのアドインにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="4c666-123">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="4c666-124">アドインを使用しているユーザーがいない場合は、削除を検討してください。</span><span class="sxs-lookup"><span data-stu-id="4c666-124">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="4c666-125">たとえば、アドインが 1 年の特定の時間にのみ使用される場合は、アドインをオフにした方が理にかなっている場合があります。</span><span class="sxs-lookup"><span data-stu-id="4c666-125">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="4c666-126">アドインを削除する</span><span class="sxs-lookup"><span data-stu-id="4c666-126">Delete an add-in</span></span>

<span data-ttu-id="4c666-127">また、展開されたアドインを削除できます。</span><span class="sxs-lookup"><span data-stu-id="4c666-127">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="4c666-128">管理センターで、[アドイン **の設定** サービス]  >  **&に移動** します。</span><span class="sxs-lookup"><span data-stu-id="4c666-128">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="4c666-129">管理センターは、統合アプリの展開エクスペリエンスに更新されています。</span><span class="sxs-lookup"><span data-stu-id="4c666-129">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="4c666-130">If you don't see the above steps, go to Centralized Deployment section by going to **Settings**  >  **Integrated apps**.</span><span class="sxs-lookup"><span data-stu-id="4c666-130">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="4c666-131">[統合アプリ] **ページの上部で** 、[アドイン] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4c666-131">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="4c666-132">展開されたアドインを選択します。</span><span class="sxs-lookup"><span data-stu-id="4c666-132">Select the deployed add-in.</span></span>

3. <span data-ttu-id="4c666-133">[アドインの **削除] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4c666-133">Click on **Delete Add-In**.</span></span> <span data-ttu-id="4c666-134">右下隅にある [アドイン] ボタンを削除します。</span><span class="sxs-lookup"><span data-stu-id="4c666-134">Remove the Add-in button on the bottom right corner.</span></span>

4. <span data-ttu-id="4c666-135">選択内容を確認し、[**アドインの削除]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="4c666-135">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="4c666-136">アドインのアクセスを編集する</span><span class="sxs-lookup"><span data-stu-id="4c666-136">Edit add-in access</span></span>

<span data-ttu-id="4c666-137">展開後、管理者はアドインへのユーザー アクセスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="4c666-137">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="4c666-138">管理センターで、[アドイン **の設定** サービス]  >  **&に移動** します。</span><span class="sxs-lookup"><span data-stu-id="4c666-138">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="4c666-139">管理センターは、統合アプリの展開エクスペリエンスに更新されています。</span><span class="sxs-lookup"><span data-stu-id="4c666-139">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="4c666-140">上記の手順が表示されな場合は、[統合アプリの設定] に移動して、[一元展開]  >  **セクションに移動します**。</span><span class="sxs-lookup"><span data-stu-id="4c666-140">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="4c666-141">[統合アプリ] **ページの上部で** 、[アドイン] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4c666-141">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="4c666-142">展開されたアドインを選択します。</span><span class="sxs-lookup"><span data-stu-id="4c666-142">Select the deployed add-in.</span></span>

3. <span data-ttu-id="4c666-143">Click on **Edit** under **Who has Access**.</span><span class="sxs-lookup"><span data-stu-id="4c666-143">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="4c666-144">変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="4c666-144">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="4c666-145">アドインのダウンロードを防止するには、すべてのクライアントで Office ストアをオフにします (Outlook を除く)</span><span class="sxs-lookup"><span data-stu-id="4c666-145">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="4c666-146">Outlook アドインのインストールは、別のプロセスによって [管理されます](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4c666-146">Outlook add-in installation is managed by a [different process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="4c666-147">組織として、新しいアドインを Office ストアからダウンロードOfficeがあります。</span><span class="sxs-lookup"><span data-stu-id="4c666-147">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="4c666-148">これは、組織で承認されたアドインのみを組織内のユーザーに展開するために、一元展開と組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="4c666-148">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="4c666-149">**アドインの取得をオフにする**</span><span class="sxs-lookup"><span data-stu-id="4c666-149">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="4c666-150">管理センターで、 [**設定**] \> [[サービス&amp;アドイン](https://go.microsoft.com/fwlink/p/?linkid=2053743)] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4c666-150">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="4c666-151">管理センターは、統合アプリの展開エクスペリエンスに更新されています。</span><span class="sxs-lookup"><span data-stu-id="4c666-151">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="4c666-152">上記の手順が表示されな場合は、[統合アプリの設定] に移動して、[一元展開]  >  **セクションに移動します**。</span><span class="sxs-lookup"><span data-stu-id="4c666-152">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="4c666-153">[統合アプリ] **ページの上部で** 、[アドイン] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4c666-153">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="4c666-154">**[ユーザー所有のアプリとサービス]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="4c666-154">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="4c666-155">ユーザーが Office ストアにアクセスできるようにするオプションをオフにします。</span><span class="sxs-lookup"><span data-stu-id="4c666-155">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="4c666-156">これにより、すべてのユーザーがストアから次のアドインを取得する必要が生じます。</span><span class="sxs-lookup"><span data-stu-id="4c666-156">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="4c666-157">Word、Excel、PowerPoint 2016 のアドインは次の場所から利用できます。</span><span class="sxs-lookup"><span data-stu-id="4c666-157">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="4c666-158">Windows</span><span class="sxs-lookup"><span data-stu-id="4c666-158">Windows</span></span>
    
  - <span data-ttu-id="4c666-159">Mac</span><span class="sxs-lookup"><span data-stu-id="4c666-159">Mac</span></span>
    
  - <span data-ttu-id="4c666-160">Office</span><span class="sxs-lookup"><span data-stu-id="4c666-160">Office</span></span>
    
    
- <span data-ttu-id="4c666-161">**AppSource** 内から取得</span><span class="sxs-lookup"><span data-stu-id="4c666-161">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="4c666-162">Microsoft 365 内のアドイン</span><span class="sxs-lookup"><span data-stu-id="4c666-162">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="4c666-163">ストアにアクセスしようとすると、次のメッセージが表示されます。申し訳ございません **。Microsoft 365** は、Office ストア アドインの個別の取得を防止するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="4c666-163">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="4c666-164">ストアのOfficeのサポートは、次のバージョンで利用できます。</span><span class="sxs-lookup"><span data-stu-id="4c666-164">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="4c666-165">Windows: 16.0.9001 - 現在利用可能です。</span><span class="sxs-lookup"><span data-stu-id="4c666-165">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="4c666-166">Mac: 16.10.18011401 - 現在利用可能です。</span><span class="sxs-lookup"><span data-stu-id="4c666-166">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="4c666-167">iOS: 2.9.18010804 - 現在利用可能です。</span><span class="sxs-lookup"><span data-stu-id="4c666-167">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="4c666-168">Web - 現在利用可能です。</span><span class="sxs-lookup"><span data-stu-id="4c666-168">The web - Currently available.</span></span>
    
<span data-ttu-id="4c666-169">これにより、管理者が一元展開を使用してアドインを管理ストアから割り当Officeされません。</span><span class="sxs-lookup"><span data-stu-id="4c666-169">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="4c666-170">ユーザーが Microsoft アカウントでサインインを行うのを防ぐには、組織のアカウントのみを使用するログオンを制限できます。</span><span class="sxs-lookup"><span data-stu-id="4c666-170">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="4c666-171">詳細については、「Office [2016」](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c666-171">For more information, see [Identity, authentication, and authorization in Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span></span>  

> [!NOTE]
> <span data-ttu-id="4c666-172">ユーザーが Office ストアにアクセスしなOfficeアドインをサイドロード [してテストを行うのを防ぐものにもなっています](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="4c666-172">Preventing users from accessing the office store will also prevent them from [Sideloading Office Add-ins for testing](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span></span>

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="4c666-173">アドインのエンド ユーザー エクスペリエンスの詳細</span><span class="sxs-lookup"><span data-stu-id="4c666-173">More about the end user experience with add-ins</span></span>

<span data-ttu-id="4c666-174">アドインを展開すると、エンド ユーザーは Office アプリケーションでアドインの使用を開始できます (「アドインのOfficeを開始する」を参照 [してください](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862))。</span><span class="sxs-lookup"><span data-stu-id="4c666-174">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="4c666-175">アドインは、アドインがサポートしているすべてのプラットフォームに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c666-175">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="4c666-p110">アドインがアドイン コマンドをサポートする場合、そのコマンドは Office のリボンに表示されます。次の例では、[ **引用の検索** ] コマンドが [ **引用** ] アドインで表示されています。</span><span class="sxs-lookup"><span data-stu-id="4c666-p110">If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Office引用付きリボンを追加する](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="4c666-179">展開されたアドインがアドイン コマンドをサポートしない場合、または展開されたアドインを表示する場合は、自分のアドインを使用して表示 **できます**。</span><span class="sxs-lookup"><span data-stu-id="4c666-179">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="4c666-180">Word 2016、Excel 2016、または PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="4c666-180">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="4c666-181">[ **マイ \> アドインの挿入] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4c666-181">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="4c666-182">Office アドイン ウィンドウの [ **管理による管理者** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="4c666-182">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="4c666-183">前に展開したアドインをダブルクリックします (この例では [ **引用文献** ])。</span><span class="sxs-lookup"><span data-stu-id="4c666-183">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="4c666-184">![[アドインの管理] Officeタブ](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="4c666-184">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="4c666-185">Outlook</span><span class="sxs-lookup"><span data-stu-id="4c666-185">In Outlook</span></span>

1. <span data-ttu-id="4c666-186">[ホーム **] リボン** で、[アドイン **の取得] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4c666-186">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="4c666-187">![Outlook の [格納] ボタン](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="4c666-187">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="4c666-188">左側のナビゲーションで、**[管理者が管理]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="4c666-188">Select **Admin-managed** in the left nav.</span></span> 

## <a name="learn-more"></a><span data-ttu-id="4c666-189">詳細情報</span><span class="sxs-lookup"><span data-stu-id="4c666-189">Learn more</span></span>

[<span data-ttu-id="4c666-190">管理センターでアドインを展開する</span><span class="sxs-lookup"><span data-stu-id="4c666-190">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

<span data-ttu-id="4c666-191">[Office アドイン](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)の作成と構築の詳細情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="4c666-191">Learn more about creating and building [Office Add-ins](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins).</span></span>
  
<span data-ttu-id="4c666-192">[アドインを管理するには、一元展開 PowerShell コマンドレットを使用します](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="4c666-192">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).</span></span>
  
[<span data-ttu-id="4c666-193">トラブルシューティング: ユーザーにアドインが表示されない</span><span class="sxs-lookup"><span data-stu-id="4c666-193">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[<span data-ttu-id="4c666-194">Microsoft Store から未成年者とアドインを取得する</span><span class="sxs-lookup"><span data-stu-id="4c666-194">Minors and acquiring add-ins from the Microsoft Store</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)
