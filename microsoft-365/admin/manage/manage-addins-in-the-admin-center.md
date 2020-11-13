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
description: 一元的なアドインを使用して組織内のユーザーやグループにアドインを展開する方法について説明します。
ms.openlocfilehash: 5521b01e059ca8ae4a97ecb094f9aa1198263701
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071479"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="5446b-103">管理センターでアドインを管理する</span><span class="sxs-lookup"><span data-stu-id="5446b-103">Manage add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="5446b-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="5446b-104">The admin center is changing.</span></span> <span data-ttu-id="5446b-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5446b-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="5446b-106">Office アドインは、ドキュメントをカスタマイズしたり、web 上の情報にアクセスする方法を合理化したりするのに役立ちます (「 [office アドインの使用を開始](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)する」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="5446b-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="5446b-107">管理者が組織内のユーザーに対してアドインを展開した後、管理者はアドインのオン/オフ、編集、削除、およびアドインへのアクセスの管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5446b-107">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="5446b-108">管理センターからのアドインのインストールの詳細については、「 [管理センターで](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)のアドインの展開」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5446b-108">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="5446b-109">アドインの状態</span><span class="sxs-lookup"><span data-stu-id="5446b-109">Add-in states</span></span>

<span data-ttu-id="5446b-110">アドインは、 **[オン** ] または [ **オフ** ] のどちらかの状態にすることができます。</span><span class="sxs-lookup"><span data-stu-id="5446b-110">An add-in can be in either the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="5446b-111">**状態**</span><span class="sxs-lookup"><span data-stu-id="5446b-111">**State**</span></span>|<span data-ttu-id="5446b-112">**状態が発生する原因**</span><span class="sxs-lookup"><span data-stu-id="5446b-112">**How the state occurs**</span></span>|<span data-ttu-id="5446b-113">**影響**</span><span class="sxs-lookup"><span data-stu-id="5446b-113">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5446b-114">**Active**</span><span class="sxs-lookup"><span data-stu-id="5446b-114">**Active**</span></span>  <br/> |<span data-ttu-id="5446b-115">管理者がアドインをアップロードし、ユーザーまたはグループに割り当てました。</span><span class="sxs-lookup"><span data-stu-id="5446b-115">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="5446b-116">アドインを割り当てられたユーザーやグループは、関連するクライアントでアドインを表示します。</span><span class="sxs-lookup"><span data-stu-id="5446b-116">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="5446b-117">**オフ**</span><span class="sxs-lookup"><span data-stu-id="5446b-117">**Turned off**</span></span>  <br/> |<span data-ttu-id="5446b-118">管理者がアドインをオフにした。</span><span class="sxs-lookup"><span data-stu-id="5446b-118">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="5446b-119">アドインを割り当てられたユーザーやグループは、そのアドインにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="5446b-119">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="5446b-120">アドインの状態が [アクティブ] に変更されると、ユーザーやグループはもう一度アクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="5446b-120">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="5446b-121">**Deleted**</span><span class="sxs-lookup"><span data-stu-id="5446b-121">**Deleted**</span></span>  <br/> |<span data-ttu-id="5446b-122">管理者がアドインを削除した。</span><span class="sxs-lookup"><span data-stu-id="5446b-122">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="5446b-123">アドインを割り当てられたユーザーやグループは、そのアドインにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="5446b-123">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="5446b-124">アドインを使用していない場合は、削除することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="5446b-124">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="5446b-125">たとえば、特定の時間帯にのみアドインが使用されている場合、アドインをオフにしても意味があります。</span><span class="sxs-lookup"><span data-stu-id="5446b-125">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="5446b-126">アドインを削除する</span><span class="sxs-lookup"><span data-stu-id="5446b-126">Delete an add-in</span></span>

<span data-ttu-id="5446b-127">展開されたアドインを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="5446b-127">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="5446b-128">管理センターで、[ **設定**  >  **サービス & アドイン** ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="5446b-128">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="5446b-129">管理センターでは、統合アプリを使用して、展開環境を更新しました。</span><span class="sxs-lookup"><span data-stu-id="5446b-129">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="5446b-130">上記の手順が表示されない場合は、[統合アプリの **設定** ] に移動して、[一元展開] セクションに移動  >  **Integrated apps** します。</span><span class="sxs-lookup"><span data-stu-id="5446b-130">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="5446b-131">[ **統合アプリ** ] ページの上部で、[ **アドイン** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5446b-131">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="5446b-132">展開されたアドインを選択します。</span><span class="sxs-lookup"><span data-stu-id="5446b-132">Select the deployed add-in.</span></span>

3. <span data-ttu-id="5446b-133">[ **アドインの削除** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5446b-133">Click on **Delete Add-In**.</span></span> <span data-ttu-id="5446b-134">右下隅にある [アドイン] ボタンを削除します。</span><span class="sxs-lookup"><span data-stu-id="5446b-134">Remove the Add-in button on the bottom right corner.</span></span>

4. <span data-ttu-id="5446b-135">選択内容を確認し、[ **アドインの削除]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="5446b-135">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="5446b-136">アドインのアクセスを編集する</span><span class="sxs-lookup"><span data-stu-id="5446b-136">Edit add-in access</span></span>

<span data-ttu-id="5446b-137">展開後、管理者はアドインへのユーザーアクセスを管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="5446b-137">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="5446b-138">管理センターで、[ **設定**  >  **サービス & アドイン** ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="5446b-138">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="5446b-139">管理センターでは、統合アプリを使用して、展開環境を更新しました。</span><span class="sxs-lookup"><span data-stu-id="5446b-139">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="5446b-140">上記の手順が表示されない場合は、[統合アプリの **設定** ] に移動して、[一元展開] セクションに移動  >  **Integrated apps** します。</span><span class="sxs-lookup"><span data-stu-id="5446b-140">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="5446b-141">[ **統合アプリ** ] ページの上部で、[ **アドイン** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5446b-141">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="5446b-142">展開されたアドインを選択します。</span><span class="sxs-lookup"><span data-stu-id="5446b-142">Select the deployed add-in.</span></span>

3. <span data-ttu-id="5446b-143">[ **アクセスできるユーザー** ] の [ **編集** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5446b-143">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="5446b-144">変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="5446b-144">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="5446b-145">すべてのクライアント (Outlook を除く) で Office ストアをオフにして、アドインのダウンロードを禁止する</span><span class="sxs-lookup"><span data-stu-id="5446b-145">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="5446b-146">Outlook アドインのインストールは、 [別のプロセス](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)で管理されます。</span><span class="sxs-lookup"><span data-stu-id="5446b-146">Outlook add-in installation is managed by a [different process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="5446b-147">組織の場合は、Office ストアから新しい Office アドインをダウンロードできないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5446b-147">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="5446b-148">これを一元展開と組み合わせて使用することにより、組織内のユーザーが組織内の承認済みアドインのみを展開するようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5446b-148">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="5446b-149">**アドインの取得を無効にするには**</span><span class="sxs-lookup"><span data-stu-id="5446b-149">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="5446b-150">管理センターで、 [ **設定** ] \> [ [サービス&amp;アドイン](https://go.microsoft.com/fwlink/p/?linkid=2053743)] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="5446b-150">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="5446b-151">管理センターでは、統合アプリを使用して、展開環境を更新しました。</span><span class="sxs-lookup"><span data-stu-id="5446b-151">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="5446b-152">上記の手順が表示されない場合は、[統合アプリの **設定** ] に移動して、[一元展開] セクションに移動  >  **Integrated apps** します。</span><span class="sxs-lookup"><span data-stu-id="5446b-152">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="5446b-153">[ **統合アプリ** ] ページの上部で、[ **アドイン** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5446b-153">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="5446b-154">**[ユーザー所有のアプリとサービス]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="5446b-154">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="5446b-155">ユーザーが Office ストアにアクセスできるようにするオプションをオフにします。</span><span class="sxs-lookup"><span data-stu-id="5446b-155">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="5446b-156">これにより、すべてのユーザーがストアから次のアドインを取得するのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="5446b-156">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="5446b-157">Word、Excel、PowerPoint 2016 用のアドインは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5446b-157">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="5446b-158">Windows</span><span class="sxs-lookup"><span data-stu-id="5446b-158">Windows</span></span>
    
  - <span data-ttu-id="5446b-159">Mac</span><span class="sxs-lookup"><span data-stu-id="5446b-159">Mac</span></span>
    
  - <span data-ttu-id="5446b-160">Office</span><span class="sxs-lookup"><span data-stu-id="5446b-160">Office</span></span>
    
    
- <span data-ttu-id="5446b-161">**Appsource** 内からの取得</span><span class="sxs-lookup"><span data-stu-id="5446b-161">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="5446b-162">Microsoft 365 内のアドイン</span><span class="sxs-lookup"><span data-stu-id="5446b-162">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="5446b-163">ストアにアクセスしようとするユーザーには、次のメッセージが表示されます。 **申し訳ございません。 Microsoft 365 は、Office ストアアドインの個別の取得を防止するように構成されています。**</span><span class="sxs-lookup"><span data-stu-id="5446b-163">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="5446b-164">Office ストアの無効化のサポートは、次のバージョンで利用できます。</span><span class="sxs-lookup"><span data-stu-id="5446b-164">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="5446b-165">Windows: 16.0.9001-現在使用可能です。</span><span class="sxs-lookup"><span data-stu-id="5446b-165">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="5446b-166">Mac: 16.10.18011401-現在利用可能です。</span><span class="sxs-lookup"><span data-stu-id="5446b-166">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="5446b-167">iOS: 2.9.18010804-現在使用可能です。</span><span class="sxs-lookup"><span data-stu-id="5446b-167">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="5446b-168">Web は現在利用できます。</span><span class="sxs-lookup"><span data-stu-id="5446b-168">The web - Currently available.</span></span>
    
<span data-ttu-id="5446b-169">これにより、管理者は一元展開を使用して Office ストアからアドインを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="5446b-169">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="5446b-170">ユーザーが Microsoft アカウントでサインインできないようにするには、組織のアカウントのみを使用するようにログオンを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="5446b-170">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="5446b-171">詳細については、「 [Office 2016 の id、認証、および承認](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5446b-171">For more information, see [Identity, authentication, and authorization in Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span></span>  

> [!NOTE]
> <span data-ttu-id="5446b-172">ユーザーが office ストアにアクセスできないようにすると、 [Office アドインのサイドローディングからテストを行う](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)こともできなくなります。</span><span class="sxs-lookup"><span data-stu-id="5446b-172">Preventing users from accessing the office store will also prevent them from [Sideloading Office Add-ins for testing](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span></span>

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="5446b-173">アドインを使用したエンドユーザーの作業の詳細</span><span class="sxs-lookup"><span data-stu-id="5446b-173">More about the end user experience with add-ins</span></span>

<span data-ttu-id="5446b-174">アドインを展開すると、エンドユーザーは Office アプリケーションでアドインを使い始めることができます (「 [Office アドインの使用を開始](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)する」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="5446b-174">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="5446b-175">アドインは、アドインがサポートするすべてのプラットフォームに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5446b-175">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="5446b-p110">アドインがアドイン コマンドをサポートする場合、そのコマンドは Office のリボンに表示されます。次の例では、[ **引用の検索** ] コマンドが [ **引用** ] アドインで表示されています。</span><span class="sxs-lookup"><span data-stu-id="5446b-p110">If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![検索引用を含む Office リボン](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="5446b-179">展開されたアドインがアドインコマンドをサポートしていない場合や、展開されたすべてのアドインを表示する場合は、 **[マイ** アドイン] で表示できます。</span><span class="sxs-lookup"><span data-stu-id="5446b-179">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="5446b-180">Word 2016、Excel 2016、または PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="5446b-180">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="5446b-181">[ **\> マイアドインの挿入** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5446b-181">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="5446b-182">Office アドイン ウィンドウの [ **管理による管理者** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="5446b-182">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="5446b-183">前に展開したアドインをダブルクリックします (この例では [ **引用文献** ])。</span><span class="sxs-lookup"><span data-stu-id="5446b-183">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="5446b-184">![[Office アドイン] ページの [管理者による管理] タブ](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="5446b-184">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="5446b-185">Outlook</span><span class="sxs-lookup"><span data-stu-id="5446b-185">In Outlook</span></span>

1. <span data-ttu-id="5446b-186">[ **ホーム** ] リボンで、[アドインの **取得** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5446b-186">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="5446b-187">![Outlook の [格納] ボタン](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="5446b-187">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="5446b-188">左側のナビゲーションで、 **[管理者が管理]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="5446b-188">Select **Admin-managed** in the left nav.</span></span> 

## <a name="learn-more"></a><span data-ttu-id="5446b-189">詳細情報</span><span class="sxs-lookup"><span data-stu-id="5446b-189">Learn more</span></span>

[<span data-ttu-id="5446b-190">管理センターでアドインを展開する</span><span class="sxs-lookup"><span data-stu-id="5446b-190">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

<span data-ttu-id="5446b-191">[Office アドイン](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)の作成と構築の詳細情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="5446b-191">Learn more about creating and building [Office Add-ins](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins).</span></span>
  
<span data-ttu-id="5446b-192">[一元展開 PowerShell コマンドレットを使用してアドインを管理](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)します。</span><span class="sxs-lookup"><span data-stu-id="5446b-192">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).</span></span>
  
[<span data-ttu-id="5446b-193">トラブルシューティング: ユーザーがアドインを表示していない</span><span class="sxs-lookup"><span data-stu-id="5446b-193">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[<span data-ttu-id="5446b-194">未成年者と Microsoft ストアからのアドインの取得</span><span class="sxs-lookup"><span data-stu-id="5446b-194">Minors and acquiring add-ins from the Microsoft Store</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)
