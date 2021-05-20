---
title: 管理センターでアドインを展開する
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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 管理センターの集中展開を使用して、組織内のユーザーとグループにアドインを展開する方法について説明します。
ms.openlocfilehash: 2d3b90a75f38a2c1146c0b0e5470c80b0af2c63f
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572275"
---
# <a name="deploy-add-ins-in-the-admin-center"></a><span data-ttu-id="530b1-103">管理センターでアドインを展開する</span><span class="sxs-lookup"><span data-stu-id="530b1-103">Deploy add-ins in the admin center</span></span>

<span data-ttu-id="530b1-104">Office アドインは、ドキュメントをカスタマイズしたり、Web 上の情報にアクセスする方法を効率化したりする際に役立ちます (「[Office アドインの使用を開始する](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="530b1-104">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="530b1-105">管理者は、Microsoft 365管理センターの集中展開機能を使用して、組織内のユーザーに対してOfficeアドインを展開できます。</span><span class="sxs-lookup"><span data-stu-id="530b1-105">As an admin, you can deploy Office add-ins for the users in your organization by using the Centralized Deployment feature in the Microsoft 365 admin center.</span></span> <span data-ttu-id="530b1-106">ほとんどの管理者が組織内のユーザーやグループにアドインを展開するには、集中展開が推奨され、機能が豊富な方法です。</span><span class="sxs-lookup"><span data-stu-id="530b1-106">Centralized Deployment is the recommended and most feature-rich way for most admins to deploy add-ins to users and groups within an organization.</span></span>

<span data-ttu-id="530b1-107">組織で集中展開をサポートできるかどうかを判断する方法の詳細については、「 アドイン [の集中展開が組織で機能するかどうかを判断する](centralized-deployment-of-add-ins.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="530b1-107">For more information on how to determine if your organization can support Centralized Deployment, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>

<span data-ttu-id="530b1-108">展開後のアドインの管理の詳細については、「[管理センターでアドインを管理する](manage-addins-in-the-admin-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="530b1-108">To learn more about managing add-ins after deployment, see [Manage add-ins in the admin center](manage-addins-in-the-admin-center.md)</span></span>
  
> [!NOTE]
>  <span data-ttu-id="530b1-109">Word の場合、ExcelとPowerPointは[、SharePoint アプリ カタログ](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog)を使用して、Microsoft 365やSharePoint アドインのサポートに接続しないオンプレミス環境のユーザーにアドインを展開します。</span><span class="sxs-lookup"><span data-stu-id="530b1-109">For Word, Excel and PowerPoint use a [SharePoint App Catalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) to deploy add-ins to users in an on-premises environment with no connection to Microsoft 365 and/or support for SharePoint add-ins required.</span></span> <span data-ttu-id="530b1-110">Outlookコントロール パネルExchange使用して、Microsoft 365に接続せずにオンプレミス環境に展開します。</span><span class="sxs-lookup"><span data-stu-id="530b1-110">For Outlook use Exchange control panel to deploy in an on-premises environment without a connection to Microsoft 365.</span></span>
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a><span data-ttu-id="530b1-111">Office アドインを展開する際に推奨される方法</span><span class="sxs-lookup"><span data-stu-id="530b1-111">Recommended approach for deploying Office add-ins</span></span>

<span data-ttu-id="530b1-112">段階的な方法を使用してアドインを展開するには、次の方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="530b1-112">To roll out add-ins by using a phased approach, we recommend the following:</span></span>
  
1. <span data-ttu-id="530b1-113">ビジネス内での利害関係者の小グループや IT 部門のメンバーを対象に、アドインをロールアウトします。</span><span class="sxs-lookup"><span data-stu-id="530b1-113">Roll out the add-in to a small set of business stakeholders and members of the IT department.</span></span> <span data-ttu-id="530b1-114">展開が成功した場合は、手順 2 に進みます。</span><span class="sxs-lookup"><span data-stu-id="530b1-114">If the deployment is successful, move to step 2.</span></span>
    
2. <span data-ttu-id="530b1-115">アドインをビジネス内の複数のユーザーにロールアウトします。</span><span class="sxs-lookup"><span data-stu-id="530b1-115">Roll out the add-in to more individuals within the business.</span></span> <span data-ttu-id="530b1-116">ここでも、結果を評価し、成功した場合は完全な展開を続行します。</span><span class="sxs-lookup"><span data-stu-id="530b1-116">Again, evaluate the results and, if successful, continue with full deployment.</span></span>
    
3. <span data-ttu-id="530b1-117">すべてのユーザーに対して完全なロールアウトを実行します。</span><span class="sxs-lookup"><span data-stu-id="530b1-117">Perform a full rollout to all users.</span></span>
    
<span data-ttu-id="530b1-118">対象ユーザーのサイズに応じて、ロールアウトステップを追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="530b1-118">Depending on the size of the target audience, you can add or remove roll-out steps.</span></span>
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a><span data-ttu-id="530b1-119">管理センターを使用して Office アドインを展開する</span><span class="sxs-lookup"><span data-stu-id="530b1-119">Deploy an Office add-in using the admin center</span></span>

<span data-ttu-id="530b1-120">作業を開始する前に、「 [アドインの集中展開が組織で機能するかどうかを判断する](centralized-deployment-of-add-ins.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="530b1-120">Before you begin, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>
  
1. <span data-ttu-id="530b1-121">管理センターで **、[設定** \> **アドイン**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="530b1-121">In the admin center, go to the **Settings** \> **Add-ins** page.</span></span> <span data-ttu-id="530b1-122">**[アドイン**] ページが表示されない場合は、[ \> **統合アプリ** 設定 アドイン \> ] ページ **に** 移動します。</span><span class="sxs-lookup"><span data-stu-id="530b1-122">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** page.</span></span>

2. <span data-ttu-id="530b1-123">ページの上部にある [ **アドインの展開** ] を選択し、[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="530b1-123">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="530b1-124">管理センターは、統合アプリの展開エクスペリエンスに更新されています。</span><span class="sxs-lookup"><span data-stu-id="530b1-124">The admin center is getting updated to deployment experience with Integrated Apps.</span></span> <span data-ttu-id="530b1-125">統合アプリはグローバル管理者にのみ表示されますが、他のユーザーにとっては古いエクスペリエンスがまだ存在します。</span><span class="sxs-lookup"><span data-stu-id="530b1-125">Integrated Apps is only visible to Global administrators, while for others the old experience still exists.</span></span> <span data-ttu-id="530b1-126">上記の手順が表示されない場合は、統合アプリを **設定** して[集中展開]セクションに進  >  **みます**。</span><span class="sxs-lookup"><span data-stu-id="530b1-126">If you don't see the above steps, go to the Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="530b1-127">[ **統合アプリ** ] ページの上部で、[ **アドイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="530b1-127">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

3. <span data-ttu-id="530b1-128">オプションを選択し、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="530b1-128">Select an option and follow the instructions.</span></span>
  
4. <span data-ttu-id="530b1-129">Office ストアからアドインを追加するオプションを選択した場合は、アドインを選択します。</span><span class="sxs-lookup"><span data-stu-id="530b1-129">If you selected the option to add an add-in from the Office Store, make your add-in selection.</span></span> </br>

    <span data-ttu-id="530b1-130">使用可能なアドインは、**カテゴリ別に** 表示 **できます。** </span><span class="sxs-lookup"><span data-stu-id="530b1-130">You can view available add-ins by categories: **Suggested for you**, **Rating**, or **Name**.</span></span> <span data-ttu-id="530b1-131">Office ストアからは、無料のアドインのみを利用できます。</span><span class="sxs-lookup"><span data-stu-id="530b1-131">Only free add-ins are available from the Office Store.</span></span> <span data-ttu-id="530b1-132">現在、有料アドインはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="530b1-132">Paid add-ins aren't supported currently.</span></span> <span data-ttu-id="530b1-133">アドインを選択したら、続行する使用条件に同意します。</span><span class="sxs-lookup"><span data-stu-id="530b1-133">After you select an add-in, accept the terms and conditions to proceed.</span></span> <br/> 

    > [!NOTE]
    > <span data-ttu-id="530b1-134">Officeストアオプションを使用すると、更新と拡張機能が自動的にユーザーに展開されます。</span><span class="sxs-lookup"><span data-stu-id="530b1-134">With the Office Store option, updates and enhancements are automatically deployed to users.</span></span>

5. <span data-ttu-id="530b1-135">次のページで、**[すべてのユーザー]**、**[特定のユーザー/グループ]**、**[自分だけ]** 選択して、アドインの展開先を指定します。</span><span class="sxs-lookup"><span data-stu-id="530b1-135">On the next page, select **Everyone**, **Specific users/groups**, or **Just me** to specify who the add-in is deployed to.</span></span> <span data-ttu-id="530b1-136">検索ボックスを使用して、特定のユーザーまたはグループを検索します。</span><span class="sxs-lookup"><span data-stu-id="530b1-136">Use the Search box to find specific users or groups.</span></span> <br/>

    > [!NOTE]
    > <span data-ttu-id="530b1-137">アドインに適用されるその他の状態については、「アドインの [状態](./manage-addins-in-the-admin-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="530b1-137">To learn about other states that apply to an add-in, see [Add-in states](./manage-addins-in-the-admin-center.md).</span></span>
  
6. <span data-ttu-id="530b1-138">**[展開]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="530b1-138">Select **Deploy**.</span></span>
  
7. <span data-ttu-id="530b1-139">アドインを展開すると、緑色のチェック マークが表示されます。</span><span class="sxs-lookup"><span data-stu-id="530b1-139">A green tick appears when the add-in is deployed.</span></span> <span data-ttu-id="530b1-140">ページの指示に従って、アドインをテストします。</span><span class="sxs-lookup"><span data-stu-id="530b1-140">Follow the on-page instructions to test the add-in.</span></span>

    > [!NOTE]
    > <span data-ttu-id="530b1-141">アプリのリボンにアドイン アイコンを表示するには、Office再起動する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="530b1-141">Users might need to relaunch Office to view the add-in icon on the app ribbon.</span></span> <span data-ttu-id="530b1-142">Outlookアドインがアプリのリボンに表示されるのに最大 24 時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="530b1-142">Outlook add-ins can take up to 24 hours to appear on app ribbons.</span></span>

8. <span data-ttu-id="530b1-143">完了したら、[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="530b1-143">When finished, select **Next**.</span></span> <span data-ttu-id="530b1-144">自分だけに展開した場合は、[ **アドインへのアクセス権を持つユーザーを変更** する] を選択して、より多くのユーザーに展開できます。</span><span class="sxs-lookup"><span data-stu-id="530b1-144">If you've deployed to just yourself, you can select **Change who has access to add-in** to deploy to more users.</span></span>

    <span data-ttu-id="530b1-145">アドインを組織の他のメンバーに展開した場合は、指示に従ってアドインの展開をお知らせします。</span><span class="sxs-lookup"><span data-stu-id="530b1-145">If you've deployed the add-in to other members of your organization, follow the instructions to announce the deployment of the add-in.</span></span> <br/>
  
    <span data-ttu-id="530b1-146">展開されたアドインが使用可能であることをユーザーとグループに通知することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="530b1-146">It's good practice to inform users and groups that the deployed add-in is available.</span></span> <span data-ttu-id="530b1-147">アドインの使用時期と使用方法を説明する電子メールを送信することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="530b1-147">Consider sending an email that describes when and how to use the add-in.</span></span> <span data-ttu-id="530b1-148">アドインに問題がある場合にユーザーを支援するヘルプ コンテンツまたは FAQ へのリンクを含めるか、リンクします。</span><span class="sxs-lookup"><span data-stu-id="530b1-148">Include or link to Help content or FAQs that might help users if they have problems with the add-in.</span></span>
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a><span data-ttu-id="530b1-149">ユーザーやグループにアドインを割り当てる時期を検討する</span><span class="sxs-lookup"><span data-stu-id="530b1-149">Considerations when assigning an add-in to users and groups</span></span>

<span data-ttu-id="530b1-150">グローバル管理者およびExchange管理者は、すべてのユーザーまたは特定のユーザーとグループにアドインを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="530b1-150">Global admins and Exchange admins can assign an add-in to everyone or to specific users and groups.</span></span> <span data-ttu-id="530b1-151">各オプションには、次のような意味があります。</span><span class="sxs-lookup"><span data-stu-id="530b1-151">Each option has implications:</span></span>
  
- <span data-ttu-id="530b1-152">**みんな** このオプションは、組織内のすべてのユーザーにアドインを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="530b1-152">**Everyone** This option assigns the add-in to every user in the organization.</span></span> <span data-ttu-id="530b1-153">対象のアドインが組織全体で汎用な場合にのみ、このオプションを慎重に使用します。</span><span class="sxs-lookup"><span data-stu-id="530b1-153">Use this option sparingly and only for add-ins that are truly universal to your organization.</span></span>

- <span data-ttu-id="530b1-154">**ユーザー** アドインを個々のユーザーに割り当ててから、新しいユーザーにアドインを展開する場合は、最初に新しいユーザーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="530b1-154">**Users** If you assign an add-in to an individual user, and then deploy the add-in to a new user, you must first add the new user.</span></span>

- <span data-ttu-id="530b1-155">**グループ** アドインをグループに割り当てると、グループに追加されたユーザーには自動的にアドインが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="530b1-155">**Groups** If you assign an add-in to a group, users who are added to the group are automatically assigned the add-in.</span></span> <span data-ttu-id="530b1-156">ユーザーがグループから削除されると、アドインへのアクセス権が失われます。</span><span class="sxs-lookup"><span data-stu-id="530b1-156">When a user is removed from a group, the user loses access to the add-in.</span></span> <span data-ttu-id="530b1-157">いずれの場合も、管理者からの追加のアクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="530b1-157">In either case, no additional action is required from the admin.</span></span>

- <span data-ttu-id="530b1-158">**俺だけ** 自分だけにアドインを割り当てると、アドインは自分のアカウントにのみ割り当てられるため、アドインのテストに最適です。</span><span class="sxs-lookup"><span data-stu-id="530b1-158">**Just me** If you assign an add-in to just yourself, the add-in is assigned to only your account, which is ideal for testing the add-in.</span></span>

<span data-ttu-id="530b1-159">組織に適したオプションは、構成によって異なります。</span><span class="sxs-lookup"><span data-stu-id="530b1-159">The right option for your organization depends on your configuration.</span></span> <span data-ttu-id="530b1-160">ただし、グループを使用して割り当てを行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="530b1-160">However, we recommend making assignments by using groups.</span></span> <span data-ttu-id="530b1-161">管理者は、個々のユーザーに毎回割り当てるのではなく、グループを使用してそれらのグループのメンバーシップを制御することで、アドインを管理する方が簡単な場合があります。</span><span class="sxs-lookup"><span data-stu-id="530b1-161">As an admin, you might find it easier to manage add-ins by using groups and controlling the membership of those groups rather than assigning individual users each time.</span></span> <span data-ttu-id="530b1-162">状況によっては、ユーザーを手動で割り当てることによって特定のユーザーに割り当てることによって、少数のユーザーへのアクセスを制限する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="530b1-162">In some situations, you might want to restrict access to a small set of users by making assignments to specific users by assigning users manually.</span></span>
  
## <a name="more-about-office-add-ins-security"></a><span data-ttu-id="530b1-163">Office アドインのセキュリティの詳細</span><span class="sxs-lookup"><span data-stu-id="530b1-163">More about Office add-ins security</span></span>

<span data-ttu-id="530b1-p117">Office アドインに結合されている XML マニフェスト ファイルは、アドインに関する一部のメタデータを含んでいますが、最も重要なのは、すべてのコードとロジックを含む Web アプリケーションを参照していることです。アドインにはさまざまな機能があります。たとえば、アドインでは次のことができます。</span><span class="sxs-lookup"><span data-stu-id="530b1-p117">Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:</span></span>
  
- <span data-ttu-id="530b1-167">データを表示する。</span><span class="sxs-lookup"><span data-stu-id="530b1-167">Display data.</span></span>

- <span data-ttu-id="530b1-168">ユーザーのドキュメントを読み取ってコンテキスト サービスを提供する。</span><span class="sxs-lookup"><span data-stu-id="530b1-168">Read a user's document to provide contextual services.</span></span>

- <span data-ttu-id="530b1-169">ユーザーのドキュメントのデータを読み書きして、そのユーザーに価値を提供する。</span><span class="sxs-lookup"><span data-stu-id="530b1-169">Read and write data to and from a user's document to provide value to that user.</span></span>

<span data-ttu-id="530b1-170">Office アドインの種類と機能の詳細については、「[Office アドイン プラットフォームの概要](/office/dev/add-ins/overview/office-add-ins)」をご覧ください (特に「Office アドインの構造」セクション)。</span><span class="sxs-lookup"><span data-stu-id="530b1-170">For more information about the types and capabilities of Office add-ins, see [Office Add-ins platform overview](/office/dev/add-ins/overview/office-add-ins), especially the section "Anatomy of an Office Add-in."</span></span>
  
<span data-ttu-id="530b1-p118">ユーザーのドキュメントを操作するため、アドインはマニフェストで必要なアクセス許可を宣言する必要があります。5 レベルの JavaScript API アクセス許可モデルが、タスク ウィンドウ アドインのユーザーにプライバシーとセキュリティの基礎を提供します。Office ストア 内のアドインの多くは ReadWriteDocument レベルで、ほとんどすべてのアドインは少なくとも ReadDocument レベルをサポートします。アクセス許可レベルの詳細については、「[コンテンツとタスク ウィンドウ アドインでの API 使用のアクセス許可の要求](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="530b1-p118">To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).</span></span>
  
<span data-ttu-id="530b1-p119">マニフェストを更新するとき、一般的に変更されるのはアドインのアイコンとテキストです。場合によっては、アドイン コマンドが変更されます。ただし、アドインのアクセス許可は変更されません。アドインのすべてのコードとロジックが実行される Web アプリケーションは、Web アプリケーションの性質上、いつでも変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="530b1-p119">When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.</span></span>
  
<span data-ttu-id="530b1-178">アドインの更新は次のように発生します。</span><span class="sxs-lookup"><span data-stu-id="530b1-178">Updates for add-ins happen as follows:</span></span>
  
- <span data-ttu-id="530b1-p120">**基幹業務アドイン:** この場合は、管理者が明示的にマニフェストをアップロードすると、アドインは管理者がメタデータの変更をサポートする新しいマニフェスト ファイルをアップロードすることを要求します。次に関連する Office アプリケーションが起動すると、アドインが更新されます。Web アプリケーションはいつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="530b1-p120">**Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.</span></span>

    > [!NOTE]
    > <span data-ttu-id="530b1-182">管理者は、更新を行うために LOB アドインを削除する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="530b1-182">Admin does not need to remove a LOB Add-in for doing an update.</span></span>   <span data-ttu-id="530b1-183">[アドイン] セクションで、管理者は、単に LOB アドインをクリックし、右下隅にある **[更新] ボタン** を選択します。</span><span class="sxs-lookup"><span data-stu-id="530b1-183">In the Add-ins section, Admin can simply click on the LOB Add-in and choose the **Update Button** in the bottom right corner.</span></span> <span data-ttu-id="530b1-184">更新プログラムは、新しいアドインのバージョンが既存のアドインのバージョンよりも大きい場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="530b1-184">Update will work only if the version of the new add-in is greater than that of the existing add-in.</span></span>

- <span data-ttu-id="530b1-p122">**Office ストア アドイン:** 管理者が Office ストア からアドインを選択した場合、アドインが Office ストア で更新されると、そのアドインは後で一元展開で更新されます。次に関連する Office アプリケーションが起動すると、アドインが更新されます。Web アプリケーションはいつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="530b1-p122">**Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.</span></span>
  
## <a name="related-content"></a><span data-ttu-id="530b1-188">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="530b1-188">Related content</span></span>

<span data-ttu-id="530b1-189">[管理センターでアドインを管理する](manage-addins-in-the-admin-center.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="530b1-189">[Manage add-ins in the admin center](manage-addins-in-the-admin-center.md) (article)</span></span>

<span data-ttu-id="530b1-190">[Word の最初の作業ウィンドウ アドイン](/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator) (記事) を作成する</span><span class="sxs-lookup"><span data-stu-id="530b1-190">[Build your first Word task pane add-in](/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator) (article)</span></span>

<span data-ttu-id="530b1-191">[未成年者と店舗からのアドインの取得](minors-and-acquiring-addins-from-the-store.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="530b1-191">[Minors and acquiring add-ins from the store](minors-and-acquiring-addins-from-the-store.md) (article)</span></span>
  
<span data-ttu-id="530b1-192">[展開の集中管理 PowerShell コマンドレットを使用してアドインを管理する](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="530b1-192">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) (article)</span></span>
  
<span data-ttu-id="530b1-193">[トラブルシューティング: ユーザーがアドインを表示しない](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (記事)</span><span class="sxs-lookup"><span data-stu-id="530b1-193">[Troubleshoot: User not seeing add-ins](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (article)</span></span>