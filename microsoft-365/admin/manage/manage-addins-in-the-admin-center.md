---
title: 管理センターでアドインを管理する
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
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 集中型アドインを使用して組織内のユーザーとグループにアドインを展開する方法について学習します。
ms.openlocfilehash: ed9086c77cdf10435bae09f76493af6058d2d758
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314389"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="a0541-103">管理センターでアドインを管理する</span><span class="sxs-lookup"><span data-stu-id="a0541-103">Manage add-ins in the admin center</span></span>

<span data-ttu-id="a0541-104">Officeアドインを使用すると、ドキュメントをカスタマイズし、Web 上の情報にアクセスする方法を合理化できます (「Office アドインの使用[を開始する」を参照してください](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862))。</span><span class="sxs-lookup"><span data-stu-id="a0541-104">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="a0541-105">管理者が組織内のユーザーにアドインを展開した後、管理者はアドインをオフまたはオン、編集、削除、およびアドインへのアクセスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="a0541-105">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="a0541-106">管理センターからのアドインのインストールの詳細については、「管理センターでアドインを展開する」 [を参照してください](./manage-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="a0541-106">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="a0541-107">アドインの状態</span><span class="sxs-lookup"><span data-stu-id="a0541-107">Add-in states</span></span>

<span data-ttu-id="a0541-108">アドインは[オン]または **[オフ]** のいずれかの状態 **にできます** 。</span><span class="sxs-lookup"><span data-stu-id="a0541-108">An add-in can be in either the **On** or **Off** state.</span></span>
  
| <span data-ttu-id="a0541-109">状態</span><span class="sxs-lookup"><span data-stu-id="a0541-109">State</span></span> | <span data-ttu-id="a0541-110">状態が発生する原因</span><span class="sxs-lookup"><span data-stu-id="a0541-110">How the state occurs</span></span> | <span data-ttu-id="a0541-111">影響</span><span class="sxs-lookup"><span data-stu-id="a0541-111">Impact</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="a0541-112">**アクティブ**</span><span class="sxs-lookup"><span data-stu-id="a0541-112">**Active**</span></span>  <br/> |<span data-ttu-id="a0541-113">管理者はアドインをアップロードし、ユーザーまたはグループに割り当てしました。</span><span class="sxs-lookup"><span data-stu-id="a0541-113">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="a0541-114">アドインを割り当てられたユーザーやグループは、関連するクライアントでアドインを表示します。</span><span class="sxs-lookup"><span data-stu-id="a0541-114">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="a0541-115">**オフ**</span><span class="sxs-lookup"><span data-stu-id="a0541-115">**Turned off**</span></span>  <br/> |<span data-ttu-id="a0541-116">管理者がアドインをオフにした。</span><span class="sxs-lookup"><span data-stu-id="a0541-116">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="a0541-117">アドインを割り当てられたユーザーやグループは、そのアドインにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="a0541-117">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="a0541-118">アドインの状態が [アクティブ] に変更されると、ユーザーやグループはもう一度アクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="a0541-118">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="a0541-119">**Deleted**</span><span class="sxs-lookup"><span data-stu-id="a0541-119">**Deleted**</span></span>  <br/> |<span data-ttu-id="a0541-120">管理者がアドインを削除した。</span><span class="sxs-lookup"><span data-stu-id="a0541-120">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="a0541-121">アドインを割り当てられたユーザーやグループは、そのアドインにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="a0541-121">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="a0541-122">アドインを使用しているユーザーがいない場合は、削除を検討してください。</span><span class="sxs-lookup"><span data-stu-id="a0541-122">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="a0541-123">たとえば、一年の特定の期間中にのみアドインを使用する場合は、アドインをオフにしてください。</span><span class="sxs-lookup"><span data-stu-id="a0541-123">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="a0541-124">アドインを削除する</span><span class="sxs-lookup"><span data-stu-id="a0541-124">Delete an add-in</span></span>

<span data-ttu-id="a0541-125">展開されたアドインを削除できます。</span><span class="sxs-lookup"><span data-stu-id="a0541-125">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="a0541-126">管理センターで、[サービス] ページ  >  **設定[&] ページに移動** します。</span><span class="sxs-lookup"><span data-stu-id="a0541-126">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a0541-127">管理センターは、統合アプリを使用した展開エクスペリエンスに更新されています。</span><span class="sxs-lookup"><span data-stu-id="a0541-127">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="a0541-128">上記の手順が表示されない場合は、「統合アプリの一元的な展開」**セクション** 設定  >  **進みます**。</span><span class="sxs-lookup"><span data-stu-id="a0541-128">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="a0541-129">[統合アプリ] ページ **の上部** で、[アドイン] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a0541-129">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="a0541-130">展開されたアドインを選択します。</span><span class="sxs-lookup"><span data-stu-id="a0541-130">Select the deployed add-in.</span></span>

3. <span data-ttu-id="a0541-131">[アドインの **削除] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="a0541-131">Click on **Delete Add-In**.</span></span> <span data-ttu-id="a0541-132">右下隅にある [アドイン] ボタンを削除します。</span><span class="sxs-lookup"><span data-stu-id="a0541-132">Remove the Add-in button on the bottom-right corner.</span></span>

4. <span data-ttu-id="a0541-133">選択内容を確認し、[**アドインの削除]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="a0541-133">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="a0541-134">アドインのアクセスを編集する</span><span class="sxs-lookup"><span data-stu-id="a0541-134">Edit add-in access</span></span>

<span data-ttu-id="a0541-135">展開後、管理者はアドインへのユーザー アクセスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="a0541-135">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="a0541-136">管理センターで、[サービス] ページ  >  **設定[&] ページに移動** します。</span><span class="sxs-lookup"><span data-stu-id="a0541-136">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a0541-137">管理センターは、統合アプリを使用した展開エクスペリエンスに更新されています。</span><span class="sxs-lookup"><span data-stu-id="a0541-137">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="a0541-138">上記の手順が表示されない場合は、「統合アプリの一元的な展開」**セクション** 設定  >  **進みます**。</span><span class="sxs-lookup"><span data-stu-id="a0541-138">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="a0541-139">[統合アプリ] ページ **の上部** で、[アドイン] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a0541-139">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="a0541-140">展開されたアドインを選択します。</span><span class="sxs-lookup"><span data-stu-id="a0541-140">Select the deployed add-in.</span></span>

3. <span data-ttu-id="a0541-141">[アクセス]**の下の** **[Who] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="a0541-141">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="a0541-142">変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="a0541-142">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="a0541-143">すべてのクライアントで Office ストアをオフにしてアドインのダウンロードを防止する (Outlook を除く)</span><span class="sxs-lookup"><span data-stu-id="a0541-143">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="a0541-144">Outlookアドインのインストールは、別のプロセスによって[管理されます](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="a0541-144">Outlook add-in installation is managed by a [different process](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins).</span></span>

<span data-ttu-id="a0541-145">組織として、新しいアドインを OfficeストアからダウンロードOfficeがあります。</span><span class="sxs-lookup"><span data-stu-id="a0541-145">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="a0541-146">これを集中展開と組み合わせて使用して、組織で承認されたアドインのみを組織内のユーザーに展開できます。</span><span class="sxs-lookup"><span data-stu-id="a0541-146">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="a0541-147">**アドインの取得をオフにする**</span><span class="sxs-lookup"><span data-stu-id="a0541-147">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="a0541-148">管理センターで、 [**設定**] \> [[サービス&amp;アドイン](https://go.microsoft.com/fwlink/p/?linkid=2053743)] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="a0541-148">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a0541-149">管理センターは、統合アプリを使用した展開エクスペリエンスに更新されています。</span><span class="sxs-lookup"><span data-stu-id="a0541-149">The admin center is getting updated to deployment experience with Integrated Apps.</span></span> <span data-ttu-id="a0541-150">上記の手順が表示されない場合は、「統合アプリの一元的な展開」**セクション** 設定  >  **進みます**。</span><span class="sxs-lookup"><span data-stu-id="a0541-150">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="a0541-151">[統合アプリ] ページ **の上部** で、[アドイン] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a0541-151">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="a0541-152">**[ユーザー所有のアプリとサービス]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="a0541-152">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="a0541-153">ユーザーが Office ストアにアクセスできるようにするオプションをオフにします。</span><span class="sxs-lookup"><span data-stu-id="a0541-153">Clear the option to let users access the Office store.</span></span>

    <span data-ttu-id="a0541-154">これにより、すべてのユーザーがストアから次のアドインを取得できます。</span><span class="sxs-lookup"><span data-stu-id="a0541-154">This will prevent all users from acquiring the following add-ins from the store.</span></span>
      
    - <span data-ttu-id="a0541-155">Word、Excel、およびPowerPoint 2016アドイン:</span><span class="sxs-lookup"><span data-stu-id="a0541-155">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
        
      - <span data-ttu-id="a0541-156">Windows</span><span class="sxs-lookup"><span data-stu-id="a0541-156">Windows</span></span>
      - <span data-ttu-id="a0541-157">Mac</span><span class="sxs-lookup"><span data-stu-id="a0541-157">Mac</span></span>
      - <span data-ttu-id="a0541-158">Office</span><span class="sxs-lookup"><span data-stu-id="a0541-158">Office</span></span>
        
        
    - <span data-ttu-id="a0541-159">AppSource 内から **始まる取得**</span><span class="sxs-lookup"><span data-stu-id="a0541-159">Acquisitions starting within **AppSource**</span></span>
        
    - <span data-ttu-id="a0541-160">アドイン内のアドインMicrosoft 365</span><span class="sxs-lookup"><span data-stu-id="a0541-160">Add-ins within Microsoft 365</span></span>
        
    <span data-ttu-id="a0541-161">ストアにアクセスしようとすると、次のメッセージが表示されます。申し訳ありませんが、Microsoft 365 は、Office ストア アドインの個別の取得を防止するように **構成されています。**</span><span class="sxs-lookup"><span data-stu-id="a0541-161">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="a0541-162">ストアをオフにOfficeサポートは、次のバージョンで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a0541-162">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="a0541-163">Windows: 16.0.9001 - 現在利用可能です。</span><span class="sxs-lookup"><span data-stu-id="a0541-163">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="a0541-164">Mac: 16.10.18011401 - 現在利用可能です。</span><span class="sxs-lookup"><span data-stu-id="a0541-164">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="a0541-165">iOS: 2.9.18010804 - 現在利用可能です。</span><span class="sxs-lookup"><span data-stu-id="a0541-165">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="a0541-166">Web - 現在利用可能です。</span><span class="sxs-lookup"><span data-stu-id="a0541-166">The web - Currently available.</span></span>
    
<span data-ttu-id="a0541-167">これにより、管理者が一元展開を使用してアドインを管理ストアから割り当Officeされません。</span><span class="sxs-lookup"><span data-stu-id="a0541-167">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>

> [!NOTE] 
> <span data-ttu-id="a0541-168">Visio Data Visualizer、Bing地図、People Graph などのアドインは、管理者がストアを無効にした場合でも、リボンに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0541-168">Add-ins such as Visio Data Visualizer, Bing Maps, and People Graph will still show up in the ribbon, even if an admin has disabled the Store.</span></span> <span data-ttu-id="a0541-169">これらのリンクを削除するには、管理者がグループ ポリシー オブジェクト (GPO) を使用してストアを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0541-169">To remove these links, administrators must disable the Store through Group Policy Object (GPO).</span></span>
  
<span data-ttu-id="a0541-170">ユーザーが Microsoft アカウントでサインインを防止するには、組織アカウントのみを使用するログオンを制限できます。</span><span class="sxs-lookup"><span data-stu-id="a0541-170">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="a0541-171">詳細については[、「Id、authentication、および authorization in Office 2016」を参照](/DeployOffice/security/identity-authentication-and-authorization-in-office)してください。</span><span class="sxs-lookup"><span data-stu-id="a0541-171">For more information, see [Identity, authentication, and authorization in Office 2016](/DeployOffice/security/identity-authentication-and-authorization-in-office).</span></span>  

> [!NOTE] 
> <span data-ttu-id="a0541-172">ユーザーが Office ストアにアクセスしなかOffice、ネットワーク共有からテストするためにアドインをサイドローディング[する機能も妨げる可能性があります](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="a0541-172">Preventing users from accessing the office store will also prevent them from [Sideloading Office Add-ins for testing from a network share](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span></span>

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="a0541-173">アドインを使用したエンド ユーザー エクスペリエンスの詳細</span><span class="sxs-lookup"><span data-stu-id="a0541-173">More about the end-user experience with add-ins</span></span>

<span data-ttu-id="a0541-174">アドインを展開すると、エンド ユーザーは Office アプリケーションでアドインの使用を開始できます (「アドインの使用を開始する[Office」を参照してください](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862))。</span><span class="sxs-lookup"><span data-stu-id="a0541-174">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="a0541-175">アドインは、アドインがサポートしているすべてのプラットフォームに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0541-175">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="a0541-p110">アドインがアドイン コマンドをサポートする場合、そのコマンドは Office のリボンに表示されます。次の例では、[ **引用の検索** ] コマンドが [ **引用** ] アドインで表示されています。</span><span class="sxs-lookup"><span data-stu-id="a0541-p110">If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Office付きリボン](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="a0541-179">展開されたアドインがアドイン コマンドをサポートしない場合、またはすべての展開されたアドインを表示する場合は、[マイ アドイン] を使用して表示 **できます**。</span><span class="sxs-lookup"><span data-stu-id="a0541-179">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="a0541-180">Word 2016、Excel 2016、または PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="a0541-180">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="a0541-181">[ **アドイン \> の挿入] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a0541-181">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="a0541-182">Office アドイン ウィンドウの [ **管理による管理者** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="a0541-182">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="a0541-183">前に展開したアドイン (この例では引用) **をダブルクリックします**。</span><span class="sxs-lookup"><span data-stu-id="a0541-183">Double-click the add-in you deployed earlier (in this example, **Citations**).</span></span>

    ![[アドイン] ページの [Office管理] タブ](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a><span data-ttu-id="a0541-185">Outlook</span><span class="sxs-lookup"><span data-stu-id="a0541-185">In Outlook</span></span>

1. <span data-ttu-id="a0541-186">[ホーム **] リボンで** 、[ **アドインの取得] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a0541-186">On the **Home** ribbon, select **Get Add-ins**.</span></span>

    ![Outlook の [格納] ボタン](../../media/getaddinsicon.png)
  
2. <span data-ttu-id="a0541-188">左側のナビゲーションで、**[管理者が管理]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="a0541-188">Select **Admin-managed** in the left nav.</span></span> 

## <a name="related-content"></a><span data-ttu-id="a0541-189">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="a0541-189">Related content</span></span>

<span data-ttu-id="a0541-190">[管理センターにアドインを展開](./manage-deployment-of-add-ins.md) する (記事)</span><span class="sxs-lookup"><span data-stu-id="a0541-190">[Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md) (article)</span></span>\
<span data-ttu-id="a0541-191">アドインの作成と構築Office[詳細](/office/dev/add-ins/overview/office-add-ins)(記事)</span><span class="sxs-lookup"><span data-stu-id="a0541-191">Learn more about creating and building [Office Add-ins](/office/dev/add-ins/overview/office-add-ins) (article)</span></span>\
<span data-ttu-id="a0541-192">[集中展開 PowerShell コマンドレットを使用してアドイン](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) を管理する (記事)</span><span class="sxs-lookup"><span data-stu-id="a0541-192">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) (article)</span></span>\
<span data-ttu-id="a0541-193">[トラブルシューティング: アドインが表示されないユーザー](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (記事)</span><span class="sxs-lookup"><span data-stu-id="a0541-193">[Troubleshoot: User not seeing add-ins](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (article)</span></span>\
<span data-ttu-id="a0541-194">[未成年者とアドインの](./minors-and-acquiring-addins-from-the-store.md)取得 (Microsoft Store)</span><span class="sxs-lookup"><span data-stu-id="a0541-194">[Minors and acquiring add-ins from the Microsoft Store](./minors-and-acquiring-addins-from-the-store.md) (article)</span></span>
