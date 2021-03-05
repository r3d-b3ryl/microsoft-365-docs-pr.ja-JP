---
title: 管理センターでアドインを展開する
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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 管理センターで集中展開を使用して、組織内のユーザーとグループにアドインを展開する方法について説明します。
ms.openlocfilehash: 4dc7552f2341097b95e763297d2f701f162f83ec
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454396"
---
# <a name="deploy-add-ins-in-the-admin-center"></a><span data-ttu-id="dfd45-103">管理センターでアドインを展開する</span><span class="sxs-lookup"><span data-stu-id="dfd45-103">Deploy add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="dfd45-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="dfd45-104">The admin center is changing.</span></span> <span data-ttu-id="dfd45-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfd45-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="dfd45-106">Office アドインは、ドキュメントをカスタマイズしたり、Web 上の情報にアクセスする方法を効率化したりする際に役立ちます (「[Office アドインの使用を開始する](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="dfd45-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="dfd45-107">管理者は、Microsoft 365 管理センター Office一元展開機能を使用して、組織内のユーザー用のアドインを展開できます。</span><span class="sxs-lookup"><span data-stu-id="dfd45-107">As an admin, you can deploy Office add-ins for the users in your organization by using the Centralized Deployment feature in the Microsoft 365 admin center.</span></span> <span data-ttu-id="dfd45-108">集中展開は、ほとんどの管理者が組織内のユーザーとグループにアドインを展開するための、推奨される機能豊富な方法です。</span><span class="sxs-lookup"><span data-stu-id="dfd45-108">Centralized Deployment is the recommended and most feature-rich way for most admins to deploy add-ins to users and groups within an organization.</span></span> 

<span data-ttu-id="dfd45-109">組織が集中展開をサポートできるかどうかを判断する方法の詳細については、「アドインの集中展開が組織に対して機能するかどうかを判断する」 [を参照してください](centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="dfd45-109">For more information on how to determine if your organization can support Centralized Deployment, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>

<span data-ttu-id="dfd45-110">展開後のアドインの管理の詳細については、「管理センターでアドインを管理する」 [を参照してください。](manage-addins-in-the-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="dfd45-110">To learn more about managing add-ins after deployment, see [Manage add-ins in the admin center](manage-addins-in-the-admin-center.md)</span></span>
  
> [!NOTE]
>  <span data-ttu-id="dfd45-111">Word では、Excel と PowerPoint は SharePoint アプリ カタログを使用して、Microsoft 365 への接続や [SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) アドインのサポートが必要なオンプレミス環境のユーザーにアドインを展開します。</span><span class="sxs-lookup"><span data-stu-id="dfd45-111">For Word, Excel and PowerPoint use a [SharePoint App Catalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) to deploy add-ins to users in an on-premises environment with no connection to Microsoft 365 and/or support for SharePoint add-ins required.</span></span> <span data-ttu-id="dfd45-112">Outlook では、Exchange コントロール パネルを使用して、Microsoft 365 に接続せずにオンプレミス環境に展開します。</span><span class="sxs-lookup"><span data-stu-id="dfd45-112">For Outlook use Exchange control panel to deploy in an on-premises environment without a connection to Microsoft 365.</span></span>
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a><span data-ttu-id="dfd45-113">Office アドインを展開する際に推奨される方法</span><span class="sxs-lookup"><span data-stu-id="dfd45-113">Recommended approach for deploying Office add-ins</span></span>

<span data-ttu-id="dfd45-114">段階的なアプローチを使用してアドインをロールアウトするには、次の手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dfd45-114">To roll out add-ins by using a phased approach, we recommend the following:</span></span>
  
1. <span data-ttu-id="dfd45-115">ビジネス内での利害関係者の小グループや IT 部門のメンバーを対象に、アドインをロールアウトします。</span><span class="sxs-lookup"><span data-stu-id="dfd45-115">Roll out the add-in to a small set of business stakeholders and members of the IT department.</span></span> <span data-ttu-id="dfd45-116">展開が成功した場合は、手順 2 に進みます。</span><span class="sxs-lookup"><span data-stu-id="dfd45-116">If the deployment is successful, move to step 2.</span></span>
    
2. <span data-ttu-id="dfd45-117">ビジネス内のより多くの個人にアドインを展開します。</span><span class="sxs-lookup"><span data-stu-id="dfd45-117">Roll out the add-in to more individuals within the business.</span></span> <span data-ttu-id="dfd45-118">再度、結果を評価し、成功した場合は完全展開を続行します。</span><span class="sxs-lookup"><span data-stu-id="dfd45-118">Again, evaluate the results and, if successful, continue with full deployment.</span></span>
    
3. <span data-ttu-id="dfd45-119">すべてのユーザーに対して完全なロールアウトを実行します。</span><span class="sxs-lookup"><span data-stu-id="dfd45-119">Perform a full rollout to all users.</span></span>
    
<span data-ttu-id="dfd45-120">対象ユーザーのサイズに応じて、ロールアウト 手順を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="dfd45-120">Depending on the size of the target audience, you can add or remove roll-out steps.</span></span>
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a><span data-ttu-id="dfd45-121">管理センターを使用して Office アドインを展開する</span><span class="sxs-lookup"><span data-stu-id="dfd45-121">Deploy an Office add-in using the admin center</span></span>

<span data-ttu-id="dfd45-122">開始する前に、「アドインの集中展開が組織で機能するかどうかを判断する」 [を参照してください](centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="dfd45-122">Before you begin, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>
  
1. <span data-ttu-id="dfd45-123">管理センターで、[設定] \> **アドイン ページに移動** します。</span><span class="sxs-lookup"><span data-stu-id="dfd45-123">In the admin center, go to the **Settings** \> **Add-ins** page.</span></span> <span data-ttu-id="dfd45-124">[アドイン] ページが表示され **ない** 場合は、[設定]  [統合アプリ アドイン] \>  \> **ページに移動** します。</span><span class="sxs-lookup"><span data-stu-id="dfd45-124">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** page.</span></span>
    
2. <span data-ttu-id="dfd45-125">ページ **の上部にある [アドインの** 展開] を選択し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="dfd45-125">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="dfd45-126">管理センターは、統合アプリを使用した展開エクスペリエンスに更新されています。</span><span class="sxs-lookup"><span data-stu-id="dfd45-126">The admin center is getting updated to deployment experience with Integrated Apps.</span></span> <span data-ttu-id="dfd45-127">統合アプリはグローバル管理者にのみ表示され、他のユーザーの場合は古いエクスペリエンスがまだ存在します。</span><span class="sxs-lookup"><span data-stu-id="dfd45-127">Integrated Apps is only visible to Global administrators, while for others the old experience still exists.</span></span> <span data-ttu-id="dfd45-128">上記の手順が表示されない場合は、[設定] 統合アプリに移動して、[集中展開]  >  **セクションに移動します**。</span><span class="sxs-lookup"><span data-stu-id="dfd45-128">If you don't see the above steps, go to the Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="dfd45-129">[統合アプリ] ページ **の上部** で、[アドイン] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dfd45-129">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="dfd45-130">オプションを選択し、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="dfd45-130">Select an option and follow the instructions.</span></span>
  
4. <span data-ttu-id="dfd45-131">[ストア] からアドインを追加するオプションを選択Office、アドインを選択します。</span><span class="sxs-lookup"><span data-stu-id="dfd45-131">If you selected the option to add an add-in from the Office Store, make your add-in selection.</span></span> </br>

    <span data-ttu-id="dfd45-132">使用可能なアドインは、カテゴリ別に表示 **できます。[** 推奨]、[ **評価**]、または [名前] **です**。</span><span class="sxs-lookup"><span data-stu-id="dfd45-132">You can view available add-ins by categories: **Suggested for you**, **Rating**, or **Name**.</span></span> <span data-ttu-id="dfd45-133">無料のアドインのみ、Officeストアから利用できます。</span><span class="sxs-lookup"><span data-stu-id="dfd45-133">Only free add-ins are available from the Office Store.</span></span> <span data-ttu-id="dfd45-134">現在、有料アドインはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="dfd45-134">Paid add-ins aren't supported currently.</span></span> <span data-ttu-id="dfd45-135">アドインを選択した後、続行する条件に同意します。</span><span class="sxs-lookup"><span data-stu-id="dfd45-135">After you select an add-in, accept the terms and conditions to proceed.</span></span> <br/> 

    > [!NOTE] 
    > <span data-ttu-id="dfd45-136">[Officeストア] オプションを使用すると、更新プログラムと拡張機能が自動的にユーザーに展開されます。</span><span class="sxs-lookup"><span data-stu-id="dfd45-136">With the Office Store option, updates and enhancements are automatically deployed to users.</span></span>

5. <span data-ttu-id="dfd45-137">次のページで、**[すべてのユーザー]**、**[特定のユーザー/グループ]**、**[自分だけ]** 選択して、アドインの展開先を指定します。</span><span class="sxs-lookup"><span data-stu-id="dfd45-137">On the next page, select **Everyone**, **Specific users/groups**, or **Just me** to specify who the add-in is deployed to.</span></span> <span data-ttu-id="dfd45-138">[検索] ボックスを使用して、特定のユーザーまたはグループを検索します。</span><span class="sxs-lookup"><span data-stu-id="dfd45-138">Use the Search box to find specific users or groups.</span></span> <br/>

    > [!NOTE] 
    > <span data-ttu-id="dfd45-139">アドインに適用されるその他の状態については、「アドインの状態 [」を参照してください](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md)。</span><span class="sxs-lookup"><span data-stu-id="dfd45-139">To learn about other states that apply to an add-in, see [Add-in states](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md).</span></span>
  
6. <span data-ttu-id="dfd45-140">**[展開]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfd45-140">Select **Deploy**.</span></span>
  
7. <span data-ttu-id="dfd45-141">アドインを展開すると、緑色の目盛りが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dfd45-141">A green tick appears when the add-in is deployed.</span></span> <span data-ttu-id="dfd45-142">ページ上の指示に従ってアドインをテストします。</span><span class="sxs-lookup"><span data-stu-id="dfd45-142">Follow the on-page instructions to test the add-in.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dfd45-143">アプリ リボンにアドイン アイコンをOfficeするには、ユーザーがアプリを再起動する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="dfd45-143">Users might need to relaunch Office to view the add-in icon on the app ribbon.</span></span> <span data-ttu-id="dfd45-144">Outlook アドインは、アプリリボンに表示するには最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dfd45-144">Outlook add-ins can take up to 24 hours to appear on app ribbons.</span></span>
    
8. <span data-ttu-id="dfd45-145">完了したら、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="dfd45-145">When finished, select **Next**.</span></span> <span data-ttu-id="dfd45-146">自分にだけ展開した場合は、[アドインへのアクセス権を持つユーザーを変更する] を選択して、より多くのユーザーに展開できます。</span><span class="sxs-lookup"><span data-stu-id="dfd45-146">If you've deployed to just yourself, you can select **Change who has access to add-in** to deploy to more users.</span></span>

    <span data-ttu-id="dfd45-147">組織の他のメンバーにアドインを展開した場合は、手順に従ってアドインの展開をアナウンスします。</span><span class="sxs-lookup"><span data-stu-id="dfd45-147">If you've deployed the add-in to other members of your organization, follow the instructions to announce the deployment of the add-in.</span></span> <br/>
  
    <span data-ttu-id="dfd45-148">展開されたアドインが利用可能なユーザーとグループに通知する方法をお試しください。</span><span class="sxs-lookup"><span data-stu-id="dfd45-148">It's good practice to inform users and groups that the deployed add-in is available.</span></span> <span data-ttu-id="dfd45-149">アドインを使用する場合と方法を説明する電子メールの送信を検討してください。</span><span class="sxs-lookup"><span data-stu-id="dfd45-149">Consider sending an email that describes when and how to use the add-in.</span></span> <span data-ttu-id="dfd45-150">ユーザーがアドインに問題がある場合に役立つ可能性のあるヘルプ コンテンツまたは FAQ を含めるか、またはリンクします。</span><span class="sxs-lookup"><span data-stu-id="dfd45-150">Include or link to Help content or FAQs that might help users if they have problems with the add-in.</span></span>
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a><span data-ttu-id="dfd45-151">ユーザーやグループにアドインを割り当てる時期を検討する</span><span class="sxs-lookup"><span data-stu-id="dfd45-151">Considerations when assigning an add-in to users and groups</span></span>

<span data-ttu-id="dfd45-152">グローバル管理者と Exchange 管理者は、すべてのユーザーまたは特定のユーザーとグループにアドインを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="dfd45-152">Global admins and Exchange admins can assign an add-in to everyone or to specific users and groups.</span></span> <span data-ttu-id="dfd45-153">各オプションには、次のような意味があります。</span><span class="sxs-lookup"><span data-stu-id="dfd45-153">Each option has implications:</span></span>
  
- <span data-ttu-id="dfd45-154">**すべてのユーザー** このオプションは、組織内のすべてのユーザーにアドインを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="dfd45-154">**Everyone** This option assigns the add-in to every user in the organization.</span></span> <span data-ttu-id="dfd45-155">対象のアドインが組織全体で汎用な場合にのみ、このオプションを慎重に使用します。</span><span class="sxs-lookup"><span data-stu-id="dfd45-155">Use this option sparingly and only for add-ins that are truly universal to your organization.</span></span> 
    
- <span data-ttu-id="dfd45-156">**ユーザー** 個々のユーザーにアドインを割り当て、そのアドインを新しいユーザーに展開する場合は、最初に新しいユーザーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfd45-156">**Users** If you assign an add-in to an individual user, and then deploy the add-in to a new user, you must first add the new user.</span></span>
    
- <span data-ttu-id="dfd45-157">**グループ** グループにアドインを割り当てると、グループに追加されたユーザーにアドインが自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="dfd45-157">**Groups** If you assign an add-in to a group, users who are added to the group are automatically assigned the add-in.</span></span> <span data-ttu-id="dfd45-158">ユーザーがグループから削除されると、ユーザーはアドインへのアクセスを失います。</span><span class="sxs-lookup"><span data-stu-id="dfd45-158">When a user is removed from a group, the user loses access to the add-in.</span></span> <span data-ttu-id="dfd45-159">いずれの場合も、管理者から追加のアクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="dfd45-159">In either case, no additional action is required from the admin.</span></span> 

- <span data-ttu-id="dfd45-160">**自分だけ** アドインを自分に割り当てる場合、アドインは自分のアカウントにのみ割り当てられるので、アドインのテストに最適です。</span><span class="sxs-lookup"><span data-stu-id="dfd45-160">**Just me** If you assign an add-in to just yourself, the add-in is assigned to only your account, which is ideal for testing the add-in.</span></span>
    
<span data-ttu-id="dfd45-161">組織の適切なオプションは、構成によって異なります。</span><span class="sxs-lookup"><span data-stu-id="dfd45-161">The right option for your organization depends on your configuration.</span></span> <span data-ttu-id="dfd45-162">ただし、グループを使用して割り当てを行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dfd45-162">However, we recommend making assignments by using groups.</span></span> <span data-ttu-id="dfd45-163">管理者は、グループを使用して、各ユーザーを個別に割り当てるよりも、それらのグループのメンバーシップを制御することでアドインを管理する方が簡単な場合があります。</span><span class="sxs-lookup"><span data-stu-id="dfd45-163">As an admin, you might find it easier to manage add-ins by using groups and controlling the membership of those groups rather than assigning individual users each time.</span></span> <span data-ttu-id="dfd45-164">場合によっては、ユーザーを手動で割り当て、特定のユーザーに割り当て、ユーザーの小さなセットへのアクセスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="dfd45-164">In some situations, you might want to restrict access to a small set of users by making assignments to specific users by assigning users manually.</span></span>
  
## <a name="more-about-office-add-ins-security"></a><span data-ttu-id="dfd45-165">アドインOfficeの詳細</span><span class="sxs-lookup"><span data-stu-id="dfd45-165">More about Office add-ins security</span></span>

<span data-ttu-id="dfd45-p118">Office アドインに結合されている XML マニフェスト ファイルは、アドインに関する一部のメタデータを含んでいますが、最も重要なのは、すべてのコードとロジックを含む Web アプリケーションを参照していることです。アドインにはさまざまな機能があります。たとえば、アドインでは次のことができます。</span><span class="sxs-lookup"><span data-stu-id="dfd45-p118">Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:</span></span>
  
- <span data-ttu-id="dfd45-169">データを表示する。</span><span class="sxs-lookup"><span data-stu-id="dfd45-169">Display data.</span></span>
    
- <span data-ttu-id="dfd45-170">ユーザーのドキュメントを読み取ってコンテキスト サービスを提供する。</span><span class="sxs-lookup"><span data-stu-id="dfd45-170">Read a user's document to provide contextual services.</span></span>
    
- <span data-ttu-id="dfd45-171">ユーザーのドキュメントのデータを読み書きして、そのユーザーに価値を提供する。</span><span class="sxs-lookup"><span data-stu-id="dfd45-171">Read and write data to and from a user's document to provide value to that user.</span></span>
    
<span data-ttu-id="dfd45-172">Office アドインの種類と機能の詳細については、「[Office アドイン プラットフォームの概要](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)」をご覧ください (特に「Office アドインの構造」セクション)。</span><span class="sxs-lookup"><span data-stu-id="dfd45-172">For more information about the types and capabilities of Office add-ins, see [Office Add-ins platform overview](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins), especially the section "Anatomy of an Office Add-in."</span></span>
  
<span data-ttu-id="dfd45-p119">ユーザーのドキュメントを操作するため、アドインはマニフェストで必要なアクセス許可を宣言する必要があります。5 レベルの JavaScript API アクセス許可モデルが、タスク ウィンドウ アドインのユーザーにプライバシーとセキュリティの基礎を提供します。Office ストア 内のアドインの多くは ReadWriteDocument レベルで、ほとんどすべてのアドインは少なくとも ReadDocument レベルをサポートします。アクセス許可レベルの詳細については、「[コンテンツとタスク ウィンドウ アドインでの API 使用のアクセス許可の要求](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dfd45-p119">To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).</span></span>
  
<span data-ttu-id="dfd45-p120">マニフェストを更新するとき、一般的に変更されるのはアドインのアイコンとテキストです。場合によっては、アドイン コマンドが変更されます。ただし、アドインのアクセス許可は変更されません。アドインのすべてのコードとロジックが実行される Web アプリケーションは、Web アプリケーションの性質上、いつでも変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dfd45-p120">When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.</span></span>
  
<span data-ttu-id="dfd45-180">アドインの更新は次のように発生します。</span><span class="sxs-lookup"><span data-stu-id="dfd45-180">Updates for add-ins happen as follows:</span></span>
  
- <span data-ttu-id="dfd45-p121">**基幹業務アドイン:** この場合は、管理者が明示的にマニフェストをアップロードすると、アドインは管理者がメタデータの変更をサポートする新しいマニフェスト ファイルをアップロードすることを要求します。次に関連する Office アプリケーションが起動すると、アドインが更新されます。Web アプリケーションはいつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="dfd45-p121">**Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="dfd45-184">管理者は、更新を実行するために LOB アドインを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfd45-184">Admin does not need to remove a LOB Add-in for doing an update.</span></span>   <span data-ttu-id="dfd45-185">[アドイン] セクションで、管理者は LOB アドインをクリックするだけで、右下隅にある **[更新]** ボタンを選択できます。</span><span class="sxs-lookup"><span data-stu-id="dfd45-185">In the Add-ins section, Admin can simply click on the LOB Add-in and choose the **Update Button** in the bottom right corner.</span></span> <span data-ttu-id="dfd45-186">更新は、新しいアドインのバージョンが既存のアドインのバージョンよりも大きい場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="dfd45-186">Update will work only if the version of the new add-in is greater than that of the existing add-in.</span></span>   
    
- <span data-ttu-id="dfd45-p123">**Office ストア アドイン:** 管理者が Office ストア からアドインを選択した場合、アドインが Office ストア で更新されると、そのアドインは後で一元展開で更新されます。次に関連する Office アプリケーションが起動すると、アドインが更新されます。Web アプリケーションはいつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="dfd45-p123">**Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.</span></span> 
  
## <a name="learn-more"></a><span data-ttu-id="dfd45-190">詳細情報</span><span class="sxs-lookup"><span data-stu-id="dfd45-190">Learn more</span></span>

[<span data-ttu-id="dfd45-191">管理センターでアドインを管理する</span><span class="sxs-lookup"><span data-stu-id="dfd45-191">Manage add-ins in the admin center</span></span>](manage-addins-in-the-admin-center.md)

<span data-ttu-id="dfd45-192">[最初の Word 作業ウィンドウ アドインをビルドします](https://docs.microsoft.com/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator)。</span><span class="sxs-lookup"><span data-stu-id="dfd45-192">[Build your first Word task pane add-in](https://docs.microsoft.com/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator).</span></span>

[<span data-ttu-id="dfd45-193">未成年者とストアからアドインを取得する</span><span class="sxs-lookup"><span data-stu-id="dfd45-193">Minors and acquiring add-ins from the store</span></span>](minors-and-acquiring-addins-from-the-store.md)
  
[<span data-ttu-id="dfd45-194">集中展開 PowerShell コマンドレットを使用してアドインを管理する</span><span class="sxs-lookup"><span data-stu-id="dfd45-194">Use Centralized Deployment PowerShell cmdlets to manage add-ins</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[<span data-ttu-id="dfd45-195">トラブルシューティング: アドインが表示されないユーザー</span><span class="sxs-lookup"><span data-stu-id="dfd45-195">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
