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
description: 管理センターで一元展開を使用して、組織内のユーザーとグループにアドインを展開する方法について説明します。
ms.openlocfilehash: ef7237f20780cb67bc84561ad8617dd8da6f8b82
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926356"
---
# <a name="deploy-add-ins-in-the-admin-center"></a><span data-ttu-id="35eac-103">管理センターでアドインを展開する</span><span class="sxs-lookup"><span data-stu-id="35eac-103">Deploy add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="35eac-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="35eac-104">The admin center is changing.</span></span> <span data-ttu-id="35eac-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35eac-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="35eac-106">Office アドインは、ドキュメントをカスタマイズしたり、Web 上の情報にアクセスする方法を効率化したりする際に役立ちます (「[Office アドインの使用を開始する](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="35eac-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="35eac-107">管理者は、Microsoft 365 管理センターの一元展開機能を使用して、組織内のユーザーの Office アドインを展開できます。</span><span class="sxs-lookup"><span data-stu-id="35eac-107">As an admin, you can deploy Office add-ins for the users in your organization by using the Centralized Deployment feature in the Microsoft 365 admin center.</span></span> <span data-ttu-id="35eac-108">一元展開は、ほとんどの管理者が組織内のユーザーとグループにアドインを展開する場合に推奨され、機能が豊富な方法です。</span><span class="sxs-lookup"><span data-stu-id="35eac-108">Centralized Deployment is the recommended and most feature-rich way for most admins to deploy add-ins to users and groups within an organization.</span></span> 

<span data-ttu-id="35eac-109">組織で一元展開をサポートできるかどうかを判断する方法の詳細については、「アドインの一元展開が組織で機能するかどうかを判断する」を [参照してください](centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="35eac-109">For more information on how to determine if your organization can support Centralized Deployment, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>

<span data-ttu-id="35eac-110">展開後のアドインの管理の詳細については、「管理センターでアドインを管理する」 [を参照してください。](manage-addins-in-the-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="35eac-110">To learn more about managing add-ins after deployment, see [Manage add-ins in the admin center](manage-addins-in-the-admin-center.md)</span></span>
  
> [!NOTE]
>  <span data-ttu-id="35eac-111">Word の場合、Excel と PowerPoint は SharePoint アプリ カタログを使用して、Microsoft 365 への接続や [SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) アドインのサポートが必要ないオンプレミス環境のユーザーにアドインを展開します。</span><span class="sxs-lookup"><span data-stu-id="35eac-111">For Word, Excel and PowerPoint use a [SharePoint App Catalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) to deploy add-ins to users in an on-premises environment with no connection to Microsoft 365 and/or support for SharePoint add-ins required.</span></span> <span data-ttu-id="35eac-112">Outlook では、Exchange コントロール パネルを使用して、Microsoft 365 に接続せずにオンプレミス環境に展開します。</span><span class="sxs-lookup"><span data-stu-id="35eac-112">For Outlook use Exchange control panel to deploy in an on-premises environment without a connection to Microsoft 365.</span></span>
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a><span data-ttu-id="35eac-113">Office アドインを展開する際に推奨される方法</span><span class="sxs-lookup"><span data-stu-id="35eac-113">Recommended approach for deploying Office add-ins</span></span>

<span data-ttu-id="35eac-114">段階的なアプローチを使用してアドインをロールアウトするには、次の方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="35eac-114">To roll out add-ins by using a phased approach, we recommend the following:</span></span>
  
1. <span data-ttu-id="35eac-115">ビジネス内での利害関係者の小グループや IT 部門のメンバーを対象に、アドインをロールアウトします。</span><span class="sxs-lookup"><span data-stu-id="35eac-115">Roll out the add-in to a small set of business stakeholders and members of the IT department.</span></span> <span data-ttu-id="35eac-116">展開が成功した場合は、手順 2 に進みます。</span><span class="sxs-lookup"><span data-stu-id="35eac-116">If the deployment is successful, move to step 2.</span></span>
    
2. <span data-ttu-id="35eac-117">ビジネス内のより多くの個人にアドインを展開します。</span><span class="sxs-lookup"><span data-stu-id="35eac-117">Roll out the add-in to more individuals within the business.</span></span> <span data-ttu-id="35eac-118">再度、結果を評価し、成功した場合は完全展開を続行します。</span><span class="sxs-lookup"><span data-stu-id="35eac-118">Again, evaluate the results and, if successful, continue with full deployment.</span></span>
    
3. <span data-ttu-id="35eac-119">すべてのユーザーに対して完全なロールアウトを実行します。</span><span class="sxs-lookup"><span data-stu-id="35eac-119">Perform a full rollout to all users.</span></span>
    
<span data-ttu-id="35eac-120">対象ユーザーのサイズに応じて、ロールアウト手順を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="35eac-120">Depending on the size of the target audience, you can add or remove roll-out steps.</span></span>
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a><span data-ttu-id="35eac-121">管理センターを使用して Office アドインを展開する</span><span class="sxs-lookup"><span data-stu-id="35eac-121">Deploy an Office add-in using the admin center</span></span>

<span data-ttu-id="35eac-122">開始する前に、「アドインの一元展開が組織で機能するかどうかを判断する」 [を参照してください](centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="35eac-122">Before you begin, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>
  
1. <span data-ttu-id="35eac-123">管理センターで、[設定アドイン] \> **ページに移動** します。</span><span class="sxs-lookup"><span data-stu-id="35eac-123">In the admin center, go to the **Settings** \> **Add-ins** page.</span></span> <span data-ttu-id="35eac-124">[アドイン] ページが表示 **されな場合** は、[統合アプリアドインの設定] \>  \> **ページに移動** します。</span><span class="sxs-lookup"><span data-stu-id="35eac-124">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** page.</span></span>
    
2. <span data-ttu-id="35eac-125">ページ **の上部にある [アドインの** 展開] を選択し、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="35eac-125">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="35eac-126">管理センターは、統合アプリの展開エクスペリエンスに更新されています。</span><span class="sxs-lookup"><span data-stu-id="35eac-126">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="35eac-127">上記の手順が表示されな場合は、[統合アプリの設定] に移動して、[一元展開]  >  **セクションに移動します**。</span><span class="sxs-lookup"><span data-stu-id="35eac-127">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="35eac-128">[統合アプリ] **ページの上部で** 、[アドイン] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="35eac-128">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="35eac-129">オプションを選択し、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="35eac-129">Select an option and follow the instructions.</span></span>
  
4. <span data-ttu-id="35eac-130">Office ストアからアドインを追加するオプションを選択した場合は、アドインを選択します。</span><span class="sxs-lookup"><span data-stu-id="35eac-130">If you selected the option to add an add-in from the Office Store, make your add-in selection.</span></span> </br>

    <span data-ttu-id="35eac-131">利用可能なアドインは、カテゴリ (推奨、評価、名前)**で表示\*\*\*\*できます**。</span><span class="sxs-lookup"><span data-stu-id="35eac-131">You can view available add-ins by categories: **Suggested for you**, **Rating**, or **Name**.</span></span> <span data-ttu-id="35eac-132">無料のアドインのみをストアからOfficeできます。</span><span class="sxs-lookup"><span data-stu-id="35eac-132">Only free add-ins are available from the Office Store.</span></span> <span data-ttu-id="35eac-133">現在、有料アドインはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="35eac-133">Paid add-ins aren't supported currently.</span></span> <span data-ttu-id="35eac-134">アドインを選択した後、続行する使用条件に同意します。</span><span class="sxs-lookup"><span data-stu-id="35eac-134">After you select an add-in, accept the terms and conditions to proceed.</span></span> <br/> 

    > [!NOTE] 
    > <span data-ttu-id="35eac-135">[ストアOfficeオプションを使用すると、更新プログラムと拡張機能がユーザーに自動的に展開されます。</span><span class="sxs-lookup"><span data-stu-id="35eac-135">With the Office Store option, updates and enhancements are automatically deployed to users.</span></span>

5. <span data-ttu-id="35eac-136">次のページで、**[すべてのユーザー]**、**[特定のユーザー/グループ]**、**[自分だけ]** 選択して、アドインの展開先を指定します。</span><span class="sxs-lookup"><span data-stu-id="35eac-136">On the next page, select **Everyone**, **Specific users/groups**, or **Just me** to specify who the add-in is deployed to.</span></span> <span data-ttu-id="35eac-137">検索ボックスを使用して、特定のユーザーまたはグループを検索します。</span><span class="sxs-lookup"><span data-stu-id="35eac-137">Use the Search box to find specific users or groups.</span></span> <br/>

    > [!NOTE] 
    > <span data-ttu-id="35eac-138">アドインに適用される他の状態については、「アドインの状態」 [を参照してください](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md)。</span><span class="sxs-lookup"><span data-stu-id="35eac-138">To learn about other states that apply to an add-in, see [Add-in states](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md).</span></span>
  
6. <span data-ttu-id="35eac-139">**[展開]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="35eac-139">Select **Deploy**.</span></span>
  
7. <span data-ttu-id="35eac-140">アドインを展開すると、緑色の目盛りが表示されます。</span><span class="sxs-lookup"><span data-stu-id="35eac-140">A green tick appears when the add-in is deployed.</span></span> <span data-ttu-id="35eac-141">ページ上の指示に従ってアドインをテストします。</span><span class="sxs-lookup"><span data-stu-id="35eac-141">Follow the on-page instructions to test the add-in.</span></span>

    > [!NOTE]
    > <span data-ttu-id="35eac-142">ユーザーは、アプリ のリボンOfficeアイコンを表示するために、アプリを再起動する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="35eac-142">Users might need to relaunch Office to view the add-in icon on the app ribbon.</span></span> <span data-ttu-id="35eac-143">Outlook アドインがアプリ リボンに表示されるのに最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="35eac-143">Outlook add-ins can take up to 24 hours to appear on app ribbons.</span></span>
    
8. <span data-ttu-id="35eac-144">完了したら、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="35eac-144">When finished, select **Next**.</span></span> <span data-ttu-id="35eac-145">自分専用に展開した場合は、[アドインにアクセスできるユーザーを変更する] を選択して、より多くのユーザーに展開できます。</span><span class="sxs-lookup"><span data-stu-id="35eac-145">If you've deployed to just yourself, you can select **Change who has access to add-in** to deploy to more users.</span></span>

    <span data-ttu-id="35eac-146">組織の他のメンバーにアドインを展開した場合は、指示に従ってアドインの展開をアナウンスします。</span><span class="sxs-lookup"><span data-stu-id="35eac-146">If you've deployed the add-in to other members of your organization, follow the instructions to announce the deployment of the add-in.</span></span> <br/>
  
    <span data-ttu-id="35eac-147">展開されたアドインが使用可能なユーザーとグループに通知する方法をお試しください。</span><span class="sxs-lookup"><span data-stu-id="35eac-147">It's good practice to inform users and groups that the deployed add-in is available.</span></span> <span data-ttu-id="35eac-148">アドインを使用する場合と方法を説明する電子メールを送信する場合を検討します。</span><span class="sxs-lookup"><span data-stu-id="35eac-148">Consider sending an email that describes when and how to use the add-in.</span></span> <span data-ttu-id="35eac-149">ユーザーがアドインに問題がある場合に役立つ可能性があるヘルプ コンテンツや FAQ を含めるか、リンクします。</span><span class="sxs-lookup"><span data-stu-id="35eac-149">Include or link to Help content or FAQs that might help users if they have problems with the add-in.</span></span>
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a><span data-ttu-id="35eac-150">ユーザーやグループにアドインを割り当てる時期を検討する</span><span class="sxs-lookup"><span data-stu-id="35eac-150">Considerations when assigning an add-in to users and groups</span></span>

<span data-ttu-id="35eac-151">管理者は、すべてのユーザー、または特定のユーザーやグループにアドインを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="35eac-151">Admins can assign an add-in to everyone or to specific users and groups.</span></span> <span data-ttu-id="35eac-152">各オプションには、次のような意味があります。</span><span class="sxs-lookup"><span data-stu-id="35eac-152">Each option has implications:</span></span>
  
- <span data-ttu-id="35eac-153">**すべてのユーザー** このオプションは、組織内のすべてのユーザーにアドインを割り当てる場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="35eac-153">**Everyone** This option assigns the add-in to every user in the organization.</span></span> <span data-ttu-id="35eac-154">対象のアドインが組織全体で汎用な場合にのみ、このオプションを慎重に使用します。</span><span class="sxs-lookup"><span data-stu-id="35eac-154">Use this option sparingly and only for add-ins that are truly universal to your organization.</span></span> 
    
- <span data-ttu-id="35eac-155">**ユーザー** アドインを個々のユーザーに割り当て、そのアドインを新しいユーザーに展開する場合は、最初に新しいユーザーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35eac-155">**Users** If you assign an add-in to an individual user, and then deploy the add-in to a new user, you must first add the new user.</span></span>
    
- <span data-ttu-id="35eac-156">**グループ** グループにアドインを割り当てると、グループに追加されたユーザーにアドインが自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="35eac-156">**Groups** If you assign an add-in to a group, users who are added to the group are automatically assigned the add-in.</span></span> <span data-ttu-id="35eac-157">ユーザーがグループから削除されると、そのユーザーはアドインへのアクセス権を失います。</span><span class="sxs-lookup"><span data-stu-id="35eac-157">When a user is removed from a group, the user loses access to the add-in.</span></span> <span data-ttu-id="35eac-158">どちらの場合も、管理者から追加の操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="35eac-158">In either case, no additional action is required from the admin.</span></span> 

- <span data-ttu-id="35eac-159">**Just me** 自分にだけアドインを割り当てる場合、アドインは自分のアカウントにのみ割り当てられます。これは、アドインのテストに最適です。</span><span class="sxs-lookup"><span data-stu-id="35eac-159">**Just me** If you assign an add-in to just yourself, the add-in is assigned to only your account, which is ideal for testing the add-in.</span></span>
    
<span data-ttu-id="35eac-160">組織に適切なオプションは、構成によって異なります。</span><span class="sxs-lookup"><span data-stu-id="35eac-160">The right option for your organization depends on your configuration.</span></span> <span data-ttu-id="35eac-161">ただし、グループを使用して割り当てを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="35eac-161">However, we recommend making assignments by using groups.</span></span> <span data-ttu-id="35eac-162">管理者は、グループを使用してそれらのグループのメンバーシップを制御することで、アドインを管理する方が、個別のユーザーを割り当てるのではなく、その度に簡単に管理できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="35eac-162">As an admin, you might find it easier to manage add-ins by using groups and controlling the membership of those groups rather than assigning individual users each time.</span></span> <span data-ttu-id="35eac-163">場合によっては、ユーザーを手動で割り当て、特定のユーザーに割り当て、小さなユーザー セットへのアクセスを制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35eac-163">In some situations, you might want to restrict access to a small set of users by making assignments to specific users by assigning users manually.</span></span>
  
## <a name="more-about-office-add-ins-security"></a><span data-ttu-id="35eac-164">アドインOfficeの詳細</span><span class="sxs-lookup"><span data-stu-id="35eac-164">More about Office add-ins security</span></span>

<span data-ttu-id="35eac-p118">Office アドインに結合されている XML マニフェスト ファイルは、アドインに関する一部のメタデータを含んでいますが、最も重要なのは、すべてのコードとロジックを含む Web アプリケーションを参照していることです。アドインにはさまざまな機能があります。たとえば、アドインでは次のことができます。</span><span class="sxs-lookup"><span data-stu-id="35eac-p118">Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:</span></span>
  
- <span data-ttu-id="35eac-168">データを表示する。</span><span class="sxs-lookup"><span data-stu-id="35eac-168">Display data.</span></span>
    
- <span data-ttu-id="35eac-169">ユーザーのドキュメントを読み取ってコンテキスト サービスを提供する。</span><span class="sxs-lookup"><span data-stu-id="35eac-169">Read a user's document to provide contextual services.</span></span>
    
- <span data-ttu-id="35eac-170">ユーザーのドキュメントのデータを読み書きして、そのユーザーに価値を提供する。</span><span class="sxs-lookup"><span data-stu-id="35eac-170">Read and write data to and from a user's document to provide value to that user.</span></span>
    
<span data-ttu-id="35eac-171">Office アドインの種類と機能の詳細については、「[Office アドイン プラットフォームの概要](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)」をご覧ください (特に「Office アドインの構造」セクション)。</span><span class="sxs-lookup"><span data-stu-id="35eac-171">For more information about the types and capabilities of Office add-ins, see [Office Add-ins platform overview](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins), especially the section "Anatomy of an Office Add-in."</span></span>
  
<span data-ttu-id="35eac-p119">ユーザーのドキュメントを操作するため、アドインはマニフェストで必要なアクセス許可を宣言する必要があります。5 レベルの JavaScript API アクセス許可モデルが、タスク ウィンドウ アドインのユーザーにプライバシーとセキュリティの基礎を提供します。Office ストア 内のアドインの多くは ReadWriteDocument レベルで、ほとんどすべてのアドインは少なくとも ReadDocument レベルをサポートします。アクセス許可レベルの詳細については、「[コンテンツとタスク ウィンドウ アドインでの API 使用のアクセス許可の要求](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="35eac-p119">To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).</span></span>
  
<span data-ttu-id="35eac-p120">マニフェストを更新するとき、一般的に変更されるのはアドインのアイコンとテキストです。場合によっては、アドイン コマンドが変更されます。ただし、アドインのアクセス許可は変更されません。アドインのすべてのコードとロジックが実行される Web アプリケーションは、Web アプリケーションの性質上、いつでも変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="35eac-p120">When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.</span></span>
  
<span data-ttu-id="35eac-179">アドインの更新は次のように発生します。</span><span class="sxs-lookup"><span data-stu-id="35eac-179">Updates for add-ins happen as follows:</span></span>
  
- <span data-ttu-id="35eac-p121">**基幹業務アドイン:** この場合は、管理者が明示的にマニフェストをアップロードすると、アドインは管理者がメタデータの変更をサポートする新しいマニフェスト ファイルをアップロードすることを要求します。次に関連する Office アプリケーションが起動すると、アドインが更新されます。Web アプリケーションはいつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="35eac-p121">**Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="35eac-183">管理者は、更新を実行するために LOB アドインを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35eac-183">Admin does not need to remove a LOB Add-in for doing an update.</span></span>   <span data-ttu-id="35eac-184">[アドイン] セクションで、管理者は LOB アドインをクリックするだけで、右下隅にある[更新] ボタンを選択できます。</span><span class="sxs-lookup"><span data-stu-id="35eac-184">In the Add-ins section, Admin can simply click on the LOB Add-in and choose the **Update Button** in the bottom right corner.</span></span> <span data-ttu-id="35eac-185">更新は、新しいアドインのバージョンが既存のアドインのバージョンより大きい場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="35eac-185">Update will work only if the version of the new add-in is greater than that of the existing add-in.</span></span>   
    
- <span data-ttu-id="35eac-p123">**Office ストア アドイン:** 管理者が Office ストア からアドインを選択した場合、アドインが Office ストア で更新されると、そのアドインは後で一元展開で更新されます。次に関連する Office アプリケーションが起動すると、アドインが更新されます。Web アプリケーションはいつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="35eac-p123">**Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.</span></span> 
  
## <a name="learn-more"></a><span data-ttu-id="35eac-189">詳細情報</span><span class="sxs-lookup"><span data-stu-id="35eac-189">Learn more</span></span>

[<span data-ttu-id="35eac-190">管理センターでアドインを管理する</span><span class="sxs-lookup"><span data-stu-id="35eac-190">Manage add-ins in the admin center</span></span>](manage-addins-in-the-admin-center.md)

<span data-ttu-id="35eac-191">[最初の Word 作業ウィンドウ アドインをビルドします](https://docs.microsoft.com/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator)。</span><span class="sxs-lookup"><span data-stu-id="35eac-191">[Build your first Word task pane add-in](https://docs.microsoft.com/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator).</span></span>

[<span data-ttu-id="35eac-192">マイナーとストアからアドインを取得する</span><span class="sxs-lookup"><span data-stu-id="35eac-192">Minors and acquiring add-ins from the store</span></span>](minors-and-acquiring-addins-from-the-store.md)
  
[<span data-ttu-id="35eac-193">一元展開 PowerShell コマンドレットを使用してアドインを管理する</span><span class="sxs-lookup"><span data-stu-id="35eac-193">Use Centralized Deployment PowerShell cmdlets to manage add-ins</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[<span data-ttu-id="35eac-194">トラブルシューティング: ユーザーにアドインが表示されない</span><span class="sxs-lookup"><span data-stu-id="35eac-194">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
