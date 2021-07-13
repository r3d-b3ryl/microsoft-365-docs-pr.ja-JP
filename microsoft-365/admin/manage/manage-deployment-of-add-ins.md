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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 管理センターで集中展開を使用して、組織内のユーザーとグループにアドインを展開する方法について説明します。
ms.openlocfilehash: 88613e593f3c8375073865ebe9b7e417c6b3f06f
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53392853"
---
# <a name="deploy-add-ins-in-the-admin-center"></a><span data-ttu-id="68127-103">管理センターでアドインを展開する</span><span class="sxs-lookup"><span data-stu-id="68127-103">Deploy add-ins in the admin center</span></span>

<span data-ttu-id="68127-104">Office アドインは、ドキュメントをカスタマイズしたり、Web 上の情報にアクセスする方法を効率化したりする際に役立ちます (「[Office アドインの使用を開始する](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="68127-104">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="68127-105">管理者は、Officeの集中展開機能を使用して、組織内のユーザーに対してMicrosoft 365 管理センター。</span><span class="sxs-lookup"><span data-stu-id="68127-105">As an admin, you can deploy Office add-ins for the users in your organization by using the Centralized Deployment feature in the Microsoft 365 admin center.</span></span> <span data-ttu-id="68127-106">集中展開は、ほとんどの管理者が組織内のユーザーとグループにアドインを展開するための、推奨される機能豊富な方法です。</span><span class="sxs-lookup"><span data-stu-id="68127-106">Centralized Deployment is the recommended and most feature-rich way for most admins to deploy add-ins to users and groups within an organization.</span></span>

<span data-ttu-id="68127-107">組織が集中展開をサポートできるかどうかを判断する方法の詳細については、「アドインの集中展開が組織に対して機能するかどうかを判断する」 [を参照してください](centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="68127-107">For more information on how to determine if your organization can support Centralized Deployment, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>

<span data-ttu-id="68127-108">展開後のアドインの管理の詳細については、「管理センターでアドインを管理する」 [を参照してください。](manage-addins-in-the-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="68127-108">To learn more about managing add-ins after deployment, see [Manage add-ins in the admin center](manage-addins-in-the-admin-center.md)</span></span>
  
> [!NOTE]
>  <span data-ttu-id="68127-109">Word の場合、Excel と PowerPoint は[SharePoint](/office/dev/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog)アプリ カタログを使用して、Microsoft 365 に接続したり、SharePoint アドインをサポートしたりする必要がないオンプレミス環境のユーザーにアドインを展開します。</span><span class="sxs-lookup"><span data-stu-id="68127-109">For Word, Excel and PowerPoint use a [SharePoint App Catalog](/office/dev/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) to deploy add-ins to users in an on-premises environment with no connection to Microsoft 365 and/or support for SharePoint add-ins required.</span></span> <span data-ttu-id="68127-110">たとえばOutlookコントロール Exchangeを使用して、ユーザーに接続せずにオンプレミス環境に展開Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="68127-110">For Outlook use Exchange control panel to deploy in an on-premises environment without a connection to Microsoft 365.</span></span>
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a><span data-ttu-id="68127-111">Office アドインを展開する際に推奨される方法</span><span class="sxs-lookup"><span data-stu-id="68127-111">Recommended approach for deploying Office add-ins</span></span>

<span data-ttu-id="68127-112">段階的なアプローチを使用してアドインをロールアウトするには、次の手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="68127-112">To roll out add-ins by using a phased approach, we recommend the following:</span></span>
  
1. <span data-ttu-id="68127-113">ビジネス内での利害関係者の小グループや IT 部門のメンバーを対象に、アドインをロールアウトします。</span><span class="sxs-lookup"><span data-stu-id="68127-113">Roll out the add-in to a small set of business stakeholders and members of the IT department.</span></span> <span data-ttu-id="68127-114">展開が成功した場合は、手順 2 に進みます。</span><span class="sxs-lookup"><span data-stu-id="68127-114">If the deployment is successful, move to step 2.</span></span>
    
2. <span data-ttu-id="68127-115">ビジネス内のより多くの個人にアドインを展開します。</span><span class="sxs-lookup"><span data-stu-id="68127-115">Roll out the add-in to more individuals within the business.</span></span> <span data-ttu-id="68127-116">再度、結果を評価し、成功した場合は完全展開を続行します。</span><span class="sxs-lookup"><span data-stu-id="68127-116">Again, evaluate the results and, if successful, continue with full deployment.</span></span>
    
3. <span data-ttu-id="68127-117">すべてのユーザーに対して完全なロールアウトを実行します。</span><span class="sxs-lookup"><span data-stu-id="68127-117">Perform a full rollout to all users.</span></span>
    
<span data-ttu-id="68127-118">対象ユーザーのサイズに応じて、ロールアウト 手順を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="68127-118">Depending on the size of the target audience, you can add or remove roll-out steps.</span></span>
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a><span data-ttu-id="68127-119">管理センターを使用して Office アドインを展開する</span><span class="sxs-lookup"><span data-stu-id="68127-119">Deploy an Office add-in using the admin center</span></span>

<span data-ttu-id="68127-120">開始する前に、「アドインの集中展開が組織で機能するかどうかを判断する」 [を参照してください](centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="68127-120">Before you begin, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>
  
1. <span data-ttu-id="68127-121">管理センターで、[アドイン] ページ **設定** \> **移動** します。</span><span class="sxs-lookup"><span data-stu-id="68127-121">In the admin center, go to the **Settings** \> **Add-ins** page.</span></span> <span data-ttu-id="68127-122">[アドイン] ページ **が表示され** ない場合は、[統合設定アドイン] ページ \>  \> **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="68127-122">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** page.</span></span>

2. <span data-ttu-id="68127-123">ページ **の上部にある [アドインの** 展開] を選択し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="68127-123">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="68127-124">管理センターは、統合アプリを使用した展開エクスペリエンスに更新されています。</span><span class="sxs-lookup"><span data-stu-id="68127-124">The admin center is getting updated to deployment experience with Integrated Apps.</span></span> <span data-ttu-id="68127-125">統合アプリはグローバル管理者にのみ表示され、他のユーザーの場合は古いエクスペリエンスがまだ存在します。</span><span class="sxs-lookup"><span data-stu-id="68127-125">Integrated Apps is only visible to Global administrators, while for others the old experience still exists.</span></span> <span data-ttu-id="68127-126">上記の手順が表示できない場合は、[統合アプリ] に移動して、[集中展開]**セクション設定**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="68127-126">If you don't see the above steps, go to the Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="68127-127">[統合アプリ] ページ **の上部** で、[アドイン] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="68127-127">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

3. <span data-ttu-id="68127-128">オプションを選択し、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="68127-128">Select an option and follow the instructions.</span></span>
  
4. <span data-ttu-id="68127-129">[ストア] からアドインを追加するオプションを選択したOfficeアドインを選択します。</span><span class="sxs-lookup"><span data-stu-id="68127-129">If you selected the option to add an add-in from the Office Store, make your add-in selection.</span></span> </br>

    <span data-ttu-id="68127-130">使用可能なアドインは、カテゴリ別に表示 **できます。[** 推奨]、[ **評価**]、または [名前] **です**。</span><span class="sxs-lookup"><span data-stu-id="68127-130">You can view available add-ins by categories: **Suggested for you**, **Rating**, or **Name**.</span></span> <span data-ttu-id="68127-131">無料のアドインのみ、Officeストアから利用できます。</span><span class="sxs-lookup"><span data-stu-id="68127-131">Only free add-ins are available from the Office Store.</span></span> <span data-ttu-id="68127-132">現在、有料アドインはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="68127-132">Paid add-ins aren't supported currently.</span></span> <span data-ttu-id="68127-133">アドインを選択した後、続行する条件に同意します。</span><span class="sxs-lookup"><span data-stu-id="68127-133">After you select an add-in, accept the terms and conditions to proceed.</span></span> <br/> 

    > [!NOTE]
    > <span data-ttu-id="68127-134">[Office] オプションを使用すると、更新プログラムと拡張機能がユーザーに自動的に展開されます。</span><span class="sxs-lookup"><span data-stu-id="68127-134">With the Office Store option, updates and enhancements are automatically deployed to users.</span></span>

5. <span data-ttu-id="68127-135">次のページで、**[すべてのユーザー]**、**[特定のユーザー/グループ]**、**[自分だけ]** 選択して、アドインの展開先を指定します。</span><span class="sxs-lookup"><span data-stu-id="68127-135">On the next page, select **Everyone**, **Specific users/groups**, or **Just me** to specify who the add-in is deployed to.</span></span> <span data-ttu-id="68127-136">[検索] ボックスを使用して、特定のユーザーまたはグループを検索します。</span><span class="sxs-lookup"><span data-stu-id="68127-136">Use the Search box to find specific users or groups.</span></span> <br/>

    > [!NOTE]
    > <span data-ttu-id="68127-137">アドインに適用されるその他の状態については、「アドインの状態 [」を参照してください](./manage-addins-in-the-admin-center.md)。</span><span class="sxs-lookup"><span data-stu-id="68127-137">To learn about other states that apply to an add-in, see [Add-in states](./manage-addins-in-the-admin-center.md).</span></span>
  
6. <span data-ttu-id="68127-138">**[展開]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="68127-138">Select **Deploy**.</span></span>
  
7. <span data-ttu-id="68127-139">アドインを展開すると、緑色の目盛りが表示されます。</span><span class="sxs-lookup"><span data-stu-id="68127-139">A green tick appears when the add-in is deployed.</span></span> <span data-ttu-id="68127-140">ページ上の指示に従ってアドインをテストします。</span><span class="sxs-lookup"><span data-stu-id="68127-140">Follow the on-page instructions to test the add-in.</span></span>

    > [!NOTE]
    > <span data-ttu-id="68127-141">アプリ リボンにアドイン アイコンをOfficeするには、ユーザーがアプリを再起動する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="68127-141">Users might need to relaunch Office to view the add-in icon on the app ribbon.</span></span> <span data-ttu-id="68127-142">Outlookアドインがアプリ リボンに表示するには、最大で 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="68127-142">Outlook add-ins can take up to 24 hours to appear on app ribbons.</span></span>

8. <span data-ttu-id="68127-143">完了したら、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="68127-143">When finished, select **Next**.</span></span> <span data-ttu-id="68127-144">自分にだけ展開した場合は、[アドインへのアクセス権を持つユーザーを変更する] を選択して、より多くのユーザーに展開できます。</span><span class="sxs-lookup"><span data-stu-id="68127-144">If you've deployed to just yourself, you can select **Change who has access to add-in** to deploy to more users.</span></span>

    <span data-ttu-id="68127-145">組織の他のメンバーにアドインを展開した場合は、手順に従ってアドインの展開をアナウンスします。</span><span class="sxs-lookup"><span data-stu-id="68127-145">If you've deployed the add-in to other members of your organization, follow the instructions to announce the deployment of the add-in.</span></span> <br/>
  
    <span data-ttu-id="68127-146">展開されたアドインが利用可能なユーザーとグループに通知する方法をお試しください。</span><span class="sxs-lookup"><span data-stu-id="68127-146">It's good practice to inform users and groups that the deployed add-in is available.</span></span> <span data-ttu-id="68127-147">アドインを使用する場合と方法を説明する電子メールの送信を検討してください。</span><span class="sxs-lookup"><span data-stu-id="68127-147">Consider sending an email that describes when and how to use the add-in.</span></span> <span data-ttu-id="68127-148">ユーザーがアドインに問題がある場合に役立つ可能性のあるヘルプ コンテンツまたは FAQ を含めるか、またはリンクします。</span><span class="sxs-lookup"><span data-stu-id="68127-148">Include or link to Help content or FAQs that might help users if they have problems with the add-in.</span></span>
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a><span data-ttu-id="68127-149">ユーザーやグループにアドインを割り当てる時期を検討する</span><span class="sxs-lookup"><span data-stu-id="68127-149">Considerations when assigning an add-in to users and groups</span></span>

<span data-ttu-id="68127-150">グローバル管理者と管理者Exchange、すべてのユーザーまたは特定のユーザーとグループにアドインを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="68127-150">Global admins and Exchange admins can assign an add-in to everyone or to specific users and groups.</span></span> <span data-ttu-id="68127-151">各オプションには、次のような意味があります。</span><span class="sxs-lookup"><span data-stu-id="68127-151">Each option has implications:</span></span>
  
- <span data-ttu-id="68127-152">**すべてのユーザー** このオプションは、組織内のすべてのユーザーにアドインを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="68127-152">**Everyone** This option assigns the add-in to every user in the organization.</span></span> <span data-ttu-id="68127-153">対象のアドインが組織全体で汎用な場合にのみ、このオプションを慎重に使用します。</span><span class="sxs-lookup"><span data-stu-id="68127-153">Use this option sparingly and only for add-ins that are truly universal to your organization.</span></span>

- <span data-ttu-id="68127-154">**ユーザー** 個々のユーザーにアドインを割り当て、そのアドインを新しいユーザーに展開する場合は、最初に新しいユーザーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68127-154">**Users** If you assign an add-in to an individual user, and then deploy the add-in to a new user, you must first add the new user.</span></span>

- <span data-ttu-id="68127-155">**グループ** グループにアドインを割り当てると、グループに追加されたユーザーにアドインが自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="68127-155">**Groups** If you assign an add-in to a group, users who are added to the group are automatically assigned the add-in.</span></span> <span data-ttu-id="68127-156">ユーザーがグループから削除されると、ユーザーはアドインへのアクセスを失います。</span><span class="sxs-lookup"><span data-stu-id="68127-156">When a user is removed from a group, the user loses access to the add-in.</span></span> <span data-ttu-id="68127-157">いずれの場合も、管理者から追加のアクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="68127-157">In either case, no additional action is required from the admin.</span></span>

- <span data-ttu-id="68127-158">**自分だけ** アドインを自分に割り当てる場合、アドインは自分のアカウントにのみ割り当てられるので、アドインのテストに最適です。</span><span class="sxs-lookup"><span data-stu-id="68127-158">**Just me** If you assign an add-in to just yourself, the add-in is assigned to only your account, which is ideal for testing the add-in.</span></span>

<span data-ttu-id="68127-159">組織の適切なオプションは、構成によって異なります。</span><span class="sxs-lookup"><span data-stu-id="68127-159">The right option for your organization depends on your configuration.</span></span> <span data-ttu-id="68127-160">ただし、グループを使用して割り当てを行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="68127-160">However, we recommend making assignments by using groups.</span></span> <span data-ttu-id="68127-161">管理者は、グループを使用して、各ユーザーを個別に割り当てるよりも、それらのグループのメンバーシップを制御することでアドインを管理する方が簡単な場合があります。</span><span class="sxs-lookup"><span data-stu-id="68127-161">As an admin, you might find it easier to manage add-ins by using groups and controlling the membership of those groups rather than assigning individual users each time.</span></span> <span data-ttu-id="68127-162">場合によっては、ユーザーを手動で割り当て、特定のユーザーに割り当て、ユーザーの小さなセットへのアクセスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="68127-162">In some situations, you might want to restrict access to a small set of users by making assignments to specific users by assigning users manually.</span></span>
  
## <a name="more-about-office-add-ins-security"></a><span data-ttu-id="68127-163">アドインOfficeの詳細</span><span class="sxs-lookup"><span data-stu-id="68127-163">More about Office add-ins security</span></span>

<span data-ttu-id="68127-p117">Office アドインに結合されている XML マニフェスト ファイルは、アドインに関する一部のメタデータを含んでいますが、最も重要なのは、すべてのコードとロジックを含む Web アプリケーションを参照していることです。アドインにはさまざまな機能があります。たとえば、アドインでは次のことができます。</span><span class="sxs-lookup"><span data-stu-id="68127-p117">Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:</span></span>
  
- <span data-ttu-id="68127-167">データを表示する。</span><span class="sxs-lookup"><span data-stu-id="68127-167">Display data.</span></span>

- <span data-ttu-id="68127-168">ユーザーのドキュメントを読み取ってコンテキスト サービスを提供する。</span><span class="sxs-lookup"><span data-stu-id="68127-168">Read a user's document to provide contextual services.</span></span>

- <span data-ttu-id="68127-169">ユーザーのドキュメントのデータを読み書きして、そのユーザーに価値を提供する。</span><span class="sxs-lookup"><span data-stu-id="68127-169">Read and write data to and from a user's document to provide value to that user.</span></span>

<span data-ttu-id="68127-170">Office アドインの種類と機能の詳細については、「[Office アドイン プラットフォームの概要](/office/dev/add-ins/overview/office-add-ins)」をご覧ください (特に「Office アドインの構造」セクション)。</span><span class="sxs-lookup"><span data-stu-id="68127-170">For more information about the types and capabilities of Office add-ins, see [Office Add-ins platform overview](/office/dev/add-ins/overview/office-add-ins), especially the section "Anatomy of an Office Add-in."</span></span>
  
<span data-ttu-id="68127-p118">ユーザーのドキュメントを操作するため、アドインはマニフェストで必要なアクセス許可を宣言する必要があります。5 レベルの JavaScript API アクセス許可モデルが、タスク ウィンドウ アドインのユーザーにプライバシーとセキュリティの基礎を提供します。Office ストア 内のアドインの多くは ReadWriteDocument レベルで、ほとんどすべてのアドインは少なくとも ReadDocument レベルをサポートします。アクセス許可レベルの詳細については、「[コンテンツとタスク ウィンドウ アドインでの API 使用のアクセス許可の要求](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="68127-p118">To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).</span></span>
  
<span data-ttu-id="68127-p119">マニフェストを更新するとき、一般的に変更されるのはアドインのアイコンとテキストです。場合によっては、アドイン コマンドが変更されます。ただし、アドインのアクセス許可は変更されません。アドインのすべてのコードとロジックが実行される Web アプリケーションは、Web アプリケーションの性質上、いつでも変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="68127-p119">When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.</span></span>
  
<span data-ttu-id="68127-178">アドインの更新は次のように発生します。</span><span class="sxs-lookup"><span data-stu-id="68127-178">Updates for add-ins happen as follows:</span></span>
  
- <span data-ttu-id="68127-p120">**基幹業務アドイン:** この場合は、管理者が明示的にマニフェストをアップロードすると、アドインは管理者がメタデータの変更をサポートする新しいマニフェスト ファイルをアップロードすることを要求します。次に関連する Office アプリケーションが起動すると、アドインが更新されます。Web アプリケーションはいつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="68127-p120">**Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.</span></span>

    > [!NOTE]
    > <span data-ttu-id="68127-182">管理者は、更新を実行するために LOB アドインを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68127-182">Admin does not need to remove a LOB Add-in for doing an update.</span></span>   <span data-ttu-id="68127-183">[アドイン] セクションで、管理者は LOB アドインをクリックするだけで、右下隅にある **[更新]** ボタンを選択できます。</span><span class="sxs-lookup"><span data-stu-id="68127-183">In the Add-ins section, Admin can simply click on the LOB Add-in and choose the **Update Button** in the bottom right corner.</span></span> <span data-ttu-id="68127-184">更新は、新しいアドインのバージョンが既存のアドインのバージョンよりも大きい場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="68127-184">Update will work only if the version of the new add-in is greater than that of the existing add-in.</span></span>

- <span data-ttu-id="68127-p122">**Office ストア アドイン:** 管理者が Office ストア からアドインを選択した場合、アドインが Office ストア で更新されると、そのアドインは後で一元展開で更新されます。次に関連する Office アプリケーションが起動すると、アドインが更新されます。Web アプリケーションはいつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="68127-p122">**Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.</span></span>
  
## <a name="related-content"></a><span data-ttu-id="68127-188">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="68127-188">Related content</span></span>

<span data-ttu-id="68127-189">[管理センターでアドインを管理](manage-addins-in-the-admin-center.md) する (記事)</span><span class="sxs-lookup"><span data-stu-id="68127-189">[Manage add-ins in the admin center](manage-addins-in-the-admin-center.md) (article)</span></span>\
<span data-ttu-id="68127-190">[最初の Word 作業ウィンドウ アドインをビルド](/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator) する (記事</span><span class="sxs-lookup"><span data-stu-id="68127-190">[Build your first Word task pane add-in](/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator) (article</span></span>\
<span data-ttu-id="68127-191">[未成年者と](minors-and-acquiring-addins-from-the-store.md) ストアからアドインを取得する (記事)\集中展開 [PowerShell](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) コマンドレットを使用してアドインを管理する (記事)</span><span class="sxs-lookup"><span data-stu-id="68127-191">[Minors and acquiring add-ins from the store](minors-and-acquiring-addins-from-the-store.md) (article)\ [Use Centralized Deployment PowerShell cmdlets to manage add-ins](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) (article)</span></span>\  
<span data-ttu-id="68127-192">[トラブルシューティング: アドインが表示されないユーザー](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (記事)</span><span class="sxs-lookup"><span data-stu-id="68127-192">[Troubleshoot: User not seeing add-ins](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (article)</span></span>