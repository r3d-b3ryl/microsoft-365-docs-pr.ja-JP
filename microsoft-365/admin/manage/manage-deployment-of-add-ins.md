---
title: 管理センターで Office 365 アドインの展開を管理する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 管理センターで一元展開を使用して、組織内のユーザーとグループにアドインを展開する方法について説明します。
ms.openlocfilehash: 4baba1504bbb7edaba1243d6e774efac81570c4f
ms.sourcegitcommit: b1ec6ba779a94ddbaab11a272e40abe1d3064532
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2020
ms.locfileid: "43165925"
---
# <a name="manage-deployment-of-office-365-add-ins-in-the-microsoft-365-admin-center"></a><span data-ttu-id="e1b76-103">Microsoft 365 管理センターでの Office 365 のアドインの展開を管理する</span><span class="sxs-lookup"><span data-stu-id="e1b76-103">Manage deployment of Office 365 add-ins in the Microsoft 365 admin center</span></span>

<span data-ttu-id="e1b76-104">Office アドインは、ドキュメントをカスタマイズしたり、Web 上の情報にアクセスする方法を効率化したりする際に役立ちます (「[Office アドインの使用を開始する](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="e1b76-104">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office Add-in](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx)).</span></span> <span data-ttu-id="e1b76-105">管理者は、組織内のユーザーに対して Office アドインを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-105">As an admin, you can deploy Office add-ins for the users in your organization.</span></span> <span data-ttu-id="e1b76-106">この操作は、Microsoft 365 管理センターの一元展開機能を使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-106">You can do this using the Centralized Deployment feature in the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="e1b76-107">一元展開は、ほとんどの管理者が組織内のユーザーやグループにアドインを展開するために推奨される最も豊富な方法です。</span><span class="sxs-lookup"><span data-stu-id="e1b76-107">Centralized Deployment is the recommended and most feature-rich way for most admins to deploy add-ins to users and groups within an organization.</span></span> <span data-ttu-id="e1b76-108">組織が集中展開をサポートできるかどうかを判断する方法の詳細については、「 [Office 365 組織でアドインの一元展開が機能](centralized-deployment-of-add-ins.md)するかどうかを判断する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1b76-108">For more information on how to determine if your organization can support Centralized Deployment, see [Determine if Centralized Deployment of add-ins works for your Office 365 organization](centralized-deployment-of-add-ins.md).</span></span>
  
<span data-ttu-id="e1b76-109">一元展開には、次のような利点があります。</span><span class="sxs-lookup"><span data-stu-id="e1b76-109">Centralized Deployment provides the following benefits:</span></span>
  
- <span data-ttu-id="e1b76-110">グローバル管理者は、ユーザー、グループ、またはテナント内のすべてのユーザーに対して、アドインを直接ユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-110">A Global admin can assign an add-in directly to a user, to multiple users via a group, or to everyone in the tenant.</span></span>
    
- <span data-ttu-id="e1b76-p103">関連する Office アプリケーションを起動すると、ユーザーのアドインが自動的にダウンロードされます。アドインがアドイン コマンドをサポートしている場合、アドインは、Office アプリケーション内のリボンに自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-p103">When the relevant Office application starts, the add-in automatically downloads for the user. If the add-in supports add-in commands, the add-in automatically appears in the Ribbon within the Office application.</span></span>
    
- <span data-ttu-id="e1b76-113">管理者がアドインをオフまたは削除した場合、またはユーザーが Azure Active Directory またはアドインが割り当てられているグループから削除された場合、アドインはユーザーに対して表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="e1b76-113">Add-ins will no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="e1b76-114">Word の場合、Excel と PowerPoint は[Sharepoint アプリカタログ](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog)を使用して、Office 365 に接続していないオンプレミス環境のユーザーにアドインを展開し、必要な sharepoint アドインをサポートします。</span><span class="sxs-lookup"><span data-stu-id="e1b76-114">For Word, Excel and PowerPoint use a [SharePoint App Catalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) to deploy add-ins to users in an on-premises environment with no connection to Office 365 and/or support for SharePoint add-ins required.</span></span> <span data-ttu-id="e1b76-115">Outlook の > Office 365 への接続を使用せずに、Exchange コントロールパネルを使用してオンプレミス環境に展開します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-115">>  For Outlook use Exchange control panel to deploy in an on-premises environment without a connection to Office 365.</span></span> > 
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a><span data-ttu-id="e1b76-116">Office アドインを展開するための推奨される方法</span><span class="sxs-lookup"><span data-stu-id="e1b76-116">Recommended approach for deploying Office add-ins</span></span>

<span data-ttu-id="e1b76-p105">アドインがスムーズに展開されるように、段階的なアプローチで、アドインをロールアウトすることをご検討ください。Microsoft では、次の方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e1b76-p105">Consider rolling out add-ins in a phased approach to help ensure your add-in deployment goes smoothly. We recommend the following plan:</span></span>
  
1. <span data-ttu-id="e1b76-p106">ビジネス内での利害関係者の小グループや IT 部門のメンバーを対象に、アドインをロールアウトします。展開が正常に行われたかどうかを評価して、正常に行われた場合は手順 2 に進みます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-p106">Roll-out the add-in to a small set of business stakeholders and members of the IT department. Evaluate if the deployment was successful, and if so, move on to step 2.</span></span>
    
2. <span data-ttu-id="e1b76-p107">アドインを使用することになる組織内の個別ユーザーに対象を広げて、アドインをロールアウトします。ここでも結果を評価して、すべて順調な場合は、次の手順に進み、完全に展開します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-p107">Roll-out to a larger set of individuals within the business who will be using the add-in. Again, evaluate results and, if all went well, go to the next step of a full deployment.</span></span>
    
3. <span data-ttu-id="e1b76-123">対象ユーザーにアドインを完全にロールアウトします。</span><span class="sxs-lookup"><span data-stu-id="e1b76-123">Full rollout to target audience of users.</span></span>
    
<span data-ttu-id="e1b76-124">ロールアウトの手順は、対象ユーザーの規模に応じて、追加または削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-124">Depending on the size of the target audience, you may want to add or remove roll-out steps.</span></span>
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a><span data-ttu-id="e1b76-125">管理センターを使用して Office アドインを展開する</span><span class="sxs-lookup"><span data-stu-id="e1b76-125">Deploy an Office add-in using the admin center</span></span>

<span data-ttu-id="e1b76-126">開始する前に、「[アドインの一元展開が Office 365 組織で動作するかどうかを判断する](centralized-deployment-of-add-ins.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1b76-126">Before you begin, see [Determine if Centralized Deployment of add-ins works for your Office 365 organization](centralized-deployment-of-add-ins.md).</span></span>

  
1. <span data-ttu-id="e1b76-127">Microsoft 365 管理センターで、[**設定** > ]**[アドイン] ページに**移動します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-127">In the Microsoft 365 admin center, go to the **Settings** > **Add-ins** page.</span></span>
    
2. <span data-ttu-id="e1b76-128">ページの上部にある [**アドインの展開**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-128">Select **Deploy Add-in** at the top of the page.</span></span> <span data-ttu-id="e1b76-129">[概要] ページで、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-129">On the overview page, select **Next**.</span></span>
    
3. <span data-ttu-id="e1b76-130">オプションを選択し、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="e1b76-130">Select an option and follow the instructions.</span></span>
  
4. <span data-ttu-id="e1b76-131">Office ストアからアドインを追加するオプションを選択した場合は、アドインを選択できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e1b76-131">If you selected the option to add an add-in from the Office Store, you can now make your add-in selection.</span></span> <span data-ttu-id="e1b76-132">[ **あなたへのおすすめ** ]、[ **評価** ]、[ **名前** ] のカテゴリから、利用可能なアドインを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-132">Notice that you can view available add-ins via categories of **Suggested for you**, **Rating**, or **Name**.</span></span> <span data-ttu-id="e1b76-133">無料のアドインのみを Office ストアから追加できます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-133">Only free add-ins are available to add from the Office Store.</span></span> <span data-ttu-id="e1b76-134">現在、有料アドインはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e1b76-134">Paid add-ins aren't supported currently.</span></span> <span data-ttu-id="e1b76-135">アドインを選択した後、次に進むには、追加の使用条件に同意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1b76-135">Once you've selected your add-in, you will need to agree to some additional terms and conditions in order to proceed.</span></span> <br/><br/> <span data-ttu-id="e1b76-136">注: Office ストアオプションを使用すると、ユーザーが操作しなくても、アドインの更新と機能拡張が自動的にユーザーに対して利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="e1b76-136">NOTE: With the Office Store option, updates and enhancements to the add-in will automatically be made available to users without your intervention.</span></span>

5. <span data-ttu-id="e1b76-137">次のページで、[**すべて**のユーザー]、[**特定のユーザー/グループ**]、または [**自分のみ**] を選択して、アドインの展開先を指定します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-137">On the next page, select **Everyone**, **Specific users/groups** or **Just me** to specify who the add-in is deployed to.</span></span> <span data-ttu-id="e1b76-138">[検索] ボックスを使用して、アドインを展開するユーザーやグループを検索します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-138">Use the Search box to find the users or groups who you want to deploy the add-in to.</span></span> <br/><span data-ttu-id="e1b76-139">メモ: アドインに適用されるその他の状態について説明します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-139">NOTE: Learn about the other states that apply to an add-in.</span></span> <span data-ttu-id="e1b76-140">このトピックで後述する「[アドインの状態](#add-in-states)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1b76-140">See [Add-in states](#add-in-states) later in this topic.</span></span>
  
6. <span data-ttu-id="e1b76-141">**[展開]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-141">Select **Deploy**.</span></span>
  
7. <span data-ttu-id="e1b76-142">アドインが展開されると、緑色の目盛りが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-142">A green tick will appear when the add-in has been deployed.</span></span> <span data-ttu-id="e1b76-143">ページ上の指示に従って、アドインが正常に展開されたことをテストできます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-143">You can follow the on-page instructions to test that the add-in has deployed successfully.</span></span>

> [!NOTE]
> <span data-ttu-id="e1b76-144">アプリのリボンにアドインアイコンが表示されるように、ユーザーが Office を再起動する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e1b76-144">Users may need to relaunch Office to see the add-in icon appear on the ribbon of app.</span></span> <span data-ttu-id="e1b76-145">Outlook アドインは、ユーザーのリボンに表示されるまでに最大12時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="e1b76-145">Outlook add-ins can take up to 12 hours to appear on users' ribbons.</span></span>
    
8. <span data-ttu-id="e1b76-146">完了したら、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-146">When finished, select **Next**.</span></span> <span data-ttu-id="e1b76-147">自分だけに展開した場合は、他のユーザーに展開するために、[**アドインにアクセスできるユーザーを変更**する] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-147">If you've deployed to just yourself, you can select **Change who has access to add-in** in order to deploy to more users.</span></span>



<span data-ttu-id="e1b76-148">アドインを自分以外の組織のメンバーに展開した場合は、「アドインの展開を効果的に通知するために表示される指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="e1b76-148">If you've deployed the add-in to members of your organization other than yourself, follow the instructions displayed in order to effectively announce the deployment of the add-in.</span></span> <br/><span data-ttu-id="e1b76-149">アドインが Office 365 のその他のアプリと共に表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="e1b76-149">You now see your add-in along with other apps in Office 365.</span></span>
  
<span data-ttu-id="e1b76-150">アドインが使用できるようになったことを知ってもらうため、アドインを展開したことをユーザーとグループに伝えることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e1b76-150">It's a good idea to inform the users and groups who you deployed the add-in to so that they know that it's available.</span></span> <span data-ttu-id="e1b76-151">アドインの利用できる時期やその利用方法、アドインの使用により、業務がよりはかどることをメールに記載して、ユーザーに送信することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="e1b76-151">Consider sending an email to them that describes when and how to use the add-in and explains how the add-in can help them do their job better.</span></span> <span data-ttu-id="e1b76-152">ユーザーがアドインに問題が発生した場合に役立つ可能性がある関連するヘルプコンテンツや Faq を含めるか、リンクします。</span><span class="sxs-lookup"><span data-stu-id="e1b76-152">Include or link to relevant Help content or FAQs that might help if users have any problems with the add-in.</span></span>
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a><span data-ttu-id="e1b76-153">ユーザーやグループにアドインを割り当てる時期を検討する</span><span class="sxs-lookup"><span data-stu-id="e1b76-153">Considerations when assigning an add-in to users and groups</span></span>

<span data-ttu-id="e1b76-p116">管理者は、すべてのユーザー、または特定のユーザーやグループにアドインを割り当てることができます。各オプションには、次のような意味があります。</span><span class="sxs-lookup"><span data-stu-id="e1b76-p116">Admins can assign an add-in to everyone or to specific users and groups. Each option has implications:</span></span>
  
- <span data-ttu-id="e1b76-p117">**すべてのユーザー**: 名前が示すように、このオプションでは、テナント内のすべてのユーザーにアドインが割り当てられます。対象のアドインが組織全体で汎用な場合にのみ、このオプションを慎重に使用します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-p117">**Everyone**: As the name implies, this option assigns the add-in to every user in the tenant. Use this option sparingly and only for add-ins that are truly universal to your organization.</span></span> 
    
- <span data-ttu-id="e1b76-p118">**ユーザー**: 管理者が個別ユーザーにアドインを割り当て、新しいユーザーにそのアドインを展開する場合、最初に新しいユーザーを追加する必要があります。ユーザーを削除する場合も同じです。</span><span class="sxs-lookup"><span data-stu-id="e1b76-p118">**Users**: If you assign an add-in to an individual user, then to deploy the add-in to a new user, you will need to first add that user. The same goes for removing users.</span></span> 
    
- <span data-ttu-id="e1b76-p119">**グループ**: グループにアドインを割り当てる場合、グループに追加されたユーザーには、自動的にアドインが割り当てられます。また、ユーザーがグループから削除されると、そのユーザーはアドインへのアクセス権を失います。どちらの場合でも、管理者には追加の操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="e1b76-p119">**Groups**: If you assign an add-in to a group, users who are added to the group will automatically be assigned the add-in. And, when a user is removed from a group, the user loses access to the add-in. In either case, no additional action is required from you as the admin.</span></span> 

- <span data-ttu-id="e1b76-163">[**自分**のみ]: 自分だけにアドインを割り当てると、そのアドインは自分のアカウントにのみ割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-163">**Just me**: If you assign an add-in to just yourself, this assigns the add-in to only your account.</span></span> <span data-ttu-id="e1b76-164">これは、最初にアドインをテストする場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="e1b76-164">This is ideal if you wish to test out the add-in first.</span></span>
    
<span data-ttu-id="e1b76-165">組織に適したオプションは、構成によって異なります。</span><span class="sxs-lookup"><span data-stu-id="e1b76-165">The option that is right for your organization depends on your configuration.</span></span> <span data-ttu-id="e1b76-166">ただし、割り当てはグループ経由で行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e1b76-166">However, we recommend making assignments via groups.</span></span> <span data-ttu-id="e1b76-167">管理者として、割り当てるたびにユーザーを変更するよりも、グループを使用してアドインを管理し、グループのメンバーシップを制御する方が簡単なためです。</span><span class="sxs-lookup"><span data-stu-id="e1b76-167">As an admin, you might find it easier to manage add-ins using groups and control the membership of those groups rather than having to change the users assigned each time.</span></span> <span data-ttu-id="e1b76-168">一方、ごく少数のユーザーにのみアクセス権を付与したい場合は、指定したユーザーにだけ割り当てるようにします。</span><span class="sxs-lookup"><span data-stu-id="e1b76-168">On the other hand, in some situations, you may want to restrict access to a very small set of users and therefore make assignments to specific users.</span></span> <span data-ttu-id="e1b76-169">このような場合は、割り当てられているユーザーを手動で管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1b76-169">As a result, you will need to manage the assigned users manually.</span></span>
  
### <a name="add-in-states"></a><span data-ttu-id="e1b76-170">アドインの状態</span><span class="sxs-lookup"><span data-stu-id="e1b76-170">Add-in states</span></span>

<span data-ttu-id="e1b76-171">管理者は、Microsoft 365 管理センターから、すべてのユーザーに対して展開するアドインをオンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-171">Admins can turn on or off the add-ins they deploy for all users from the Microsoft 365 admin center.</span></span>

1.    <span data-ttu-id="e1b76-172">管理センターで、[ **設定** >] **[アドイン] ページに**移動します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-172">In the admin center, go to the **Settings** > **Add-ins** page.</span></span> 
2.    <span data-ttu-id="e1b76-173">展開されたアドインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-173">Select the deployed add-in.</span></span> 
3.    <span data-ttu-id="e1b76-174">[**状態**の切り替え] をクリックして、**アドインをオンまたは\*\*\*\*オフ**にします。</span><span class="sxs-lookup"><span data-stu-id="e1b76-174">Click the **Status** toggle to turn the add-in **On** or **Off**.</span></span> 
4.    <span data-ttu-id="e1b76-175">変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-175">Save the changes.</span></span>  

<span data-ttu-id="e1b76-176">3つのアドイン状態のいずれかを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-176">One of three add-in states is also available.</span></span>
 
|<span data-ttu-id="e1b76-177">**状態**</span><span class="sxs-lookup"><span data-stu-id="e1b76-177">**State**</span></span>|<span data-ttu-id="e1b76-178">**状態が発生する原因**</span><span class="sxs-lookup"><span data-stu-id="e1b76-178">**How the state occurs**</span></span>|<span data-ttu-id="e1b76-179">**影響**</span><span class="sxs-lookup"><span data-stu-id="e1b76-179">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e1b76-180">**アクティブ**</span><span class="sxs-lookup"><span data-stu-id="e1b76-180">**Active**</span></span>  <br/> |<span data-ttu-id="e1b76-181">管理者がアドインをアップロードし、ユーザーまたはグループに割り当てました。</span><span class="sxs-lookup"><span data-stu-id="e1b76-181">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="e1b76-182">アドインを割り当てられたユーザーやグループは、関連するクライアントでアドインを表示します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-182">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="e1b76-183">**オフ**</span><span class="sxs-lookup"><span data-stu-id="e1b76-183">**Turned off**</span></span>  <br/> |<span data-ttu-id="e1b76-184">管理者がアドインをオフにした。</span><span class="sxs-lookup"><span data-stu-id="e1b76-184">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="e1b76-185">アドインを割り当てられたユーザーやグループは、そのアドインにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="e1b76-185">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="e1b76-186">アドインの状態が [**アクティブ**] に変更された場合は、ユーザーとグループが再度アクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="e1b76-186">If the add-in state is changed to **Active**, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="e1b76-187">**Deleted**</span><span class="sxs-lookup"><span data-stu-id="e1b76-187">**Deleted**</span></span>  <br/> |<span data-ttu-id="e1b76-188">管理者がアドインを削除した。</span><span class="sxs-lookup"><span data-stu-id="e1b76-188">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="e1b76-189">アドインを割り当てられたユーザーやグループは、そのアドインにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="e1b76-189">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="e1b76-190">他のアドインを使用していない場合は、アドインを削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e1b76-190">Consider deleting an add-in if no one is using it any more.</span></span> <span data-ttu-id="e1b76-191">1 年のうち特定期間のみアドインを使用する場合は、オフにするのも一案です。</span><span class="sxs-lookup"><span data-stu-id="e1b76-191">Turning off an add-in may make sense if an add-in is used only during specific times of the year.</span></span>
  
### <a name="security-of-office-add-ins"></a><span data-ttu-id="e1b76-192">Office アドインのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="e1b76-192">Security of Office add-ins</span></span>

<span data-ttu-id="e1b76-p123">Office アドインに結合されている XML マニフェスト ファイルは、アドインに関する一部のメタデータを含んでいますが、最も重要なのは、すべてのコードとロジックを含む Web アプリケーションを参照していることです。アドインにはさまざまな機能があります。たとえば、アドインでは次のことができます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-p123">Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:</span></span>
  
- <span data-ttu-id="e1b76-196">データを表示する。</span><span class="sxs-lookup"><span data-stu-id="e1b76-196">Display data.</span></span>
    
- <span data-ttu-id="e1b76-197">ユーザーのドキュメントを読み取ってコンテキスト サービスを提供する。</span><span class="sxs-lookup"><span data-stu-id="e1b76-197">Read a user's document to provide contextual services.</span></span>
    
- <span data-ttu-id="e1b76-198">ユーザーのドキュメントのデータを読み書きして、そのユーザーに価値を提供する。</span><span class="sxs-lookup"><span data-stu-id="e1b76-198">Read and write data to and from a user's document to provide value to that user.</span></span>
    
<span data-ttu-id="e1b76-199">Office アドインの種類と機能の詳細については、「[Office アドイン プラットフォームの概要](https://go.microsoft.com/fwlink/p/?linkid=846362)」をご覧ください (特に「Office アドインの構造」セクション)。</span><span class="sxs-lookup"><span data-stu-id="e1b76-199">For more information about the types and capabilities of Office add-ins, see [Office Add-ins platform overview](https://go.microsoft.com/fwlink/p/?linkid=846362), especially the section "Anatomy of an Office Add-in."</span></span>
  
<span data-ttu-id="e1b76-p124">ユーザーのドキュメントを操作するため、アドインはマニフェストで必要なアクセス許可を宣言する必要があります。5 レベルの JavaScript API アクセス許可モデルが、タスク ウィンドウ アドインのユーザーにプライバシーとセキュリティの基礎を提供します。Office ストア 内のアドインの多くは ReadWriteDocument レベルで、ほとんどすべてのアドインは少なくとも ReadDocument レベルをサポートします。アクセス許可レベルの詳細については、「[コンテンツとタスク ウィンドウ アドインでの API 使用のアクセス許可の要求](https://go.microsoft.com/fwlink/p/?linkid=848863)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e1b76-p124">To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](https://go.microsoft.com/fwlink/p/?linkid=848863).</span></span>
  
<span data-ttu-id="e1b76-p125">マニフェストを更新するとき、一般的に変更されるのはアドインのアイコンとテキストです。場合によっては、アドイン コマンドが変更されます。ただし、アドインのアクセス許可は変更されません。アドインのすべてのコードとロジックが実行される Web アプリケーションは、Web アプリケーションの性質上、いつでも変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e1b76-p125">When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.</span></span>
  
<span data-ttu-id="e1b76-207">アドインの更新は次のように発生します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-207">Updates for add-ins happen as follows:</span></span>
  
- <span data-ttu-id="e1b76-p126">**基幹業務アドイン:** この場合は、管理者が明示的にマニフェストをアップロードすると、アドインは管理者がメタデータの変更をサポートする新しいマニフェスト ファイルをアップロードすることを要求します。次に関連する Office アプリケーションが起動すると、アドインが更新されます。Web アプリケーションはいつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-p126">**Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="e1b76-211">管理者は更新を実行するために LOB アドインを削除する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e1b76-211">Admin does not need to remove a LOB Add-in for doing an update.</span></span>   <span data-ttu-id="e1b76-212">[アドイン] セクションで、管理者は LOB アドインをクリックするだけで、右下隅の [**更新] ボタン**を選択できます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-212">In the Add-ins section, Admin can simply click on the LOB Add-in and choose the **Update Button** in the bottom right corner.</span></span> <span data-ttu-id="e1b76-213">更新プログラムは、新しいアドインのバージョンが既存のアドインのバージョンよりも大きい場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-213">Update will work only if the version of the new add-in is greater than that of the existing add-in.</span></span>   
    
- <span data-ttu-id="e1b76-p128">**Office ストア アドイン:** 管理者が Office ストア からアドインを選択した場合、アドインが Office ストア で更新されると、そのアドインは後で一元展開で更新されます。次に関連する Office アプリケーションが起動すると、アドインが更新されます。Web アプリケーションはいつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-p128">**Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.</span></span> 

### <a name="edit-add-in-access"></a><span data-ttu-id="e1b76-217">アドインへのアクセスを編集する</span><span class="sxs-lookup"><span data-stu-id="e1b76-217">Edit Add-in access</span></span>

<span data-ttu-id="e1b76-218">展開後、管理者はアドインへのユーザーアクセスを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-218">Post deployment, admins can also modify the user access to add-ins.</span></span>

1. <span data-ttu-id="e1b76-219">管理センターで、[**設定** > **サービス & アドイン**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-219">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

2. <span data-ttu-id="e1b76-220">展開されたアドインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-220">Select the deployed add-in.</span></span>

3. <span data-ttu-id="e1b76-221">[**アクセスできるユーザー**] の [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1b76-221">Click on **Edit** under **Who has Access**.</span></span>
4. <span data-ttu-id="e1b76-222">変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-222">Save the changes.</span></span>
    
### <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="e1b76-223">すべてのクライアント (Outlook を除く) で Office ストアをオフにして、アドインのダウンロードを禁止する</span><span class="sxs-lookup"><span data-stu-id="e1b76-223">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="e1b76-224">Outlook アドインのインストールは、[別のプロセス](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)で管理されます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-224">Outlook add-in installation is managed by a [different process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="e1b76-225">組織の場合は、Office ストアから新しい Office アドインをダウンロードできないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1b76-225">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="e1b76-226">これを一元展開と組み合わせて使用することにより、組織内のユーザーが組織内の承認済みアドインのみを展開するようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-226">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="e1b76-227">アドインの取得を無効にするには:</span><span class="sxs-lookup"><span data-stu-id="e1b76-227">To turn off add-in acquisition:</span></span>
  
1. <span data-ttu-id="e1b76-228">管理センターで、 [**設定**] \> [[サービス&amp;アドイン](https://go.microsoft.com/fwlink/p/?linkid=2053743)] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-228">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>
    
3. <span data-ttu-id="e1b76-229">**ユーザーが所有しているアプリとサービス**を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-229">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="e1b76-230">ユーザーが Office ストアにアクセスできるようにするには、このオプションをオフにします。</span><span class="sxs-lookup"><span data-stu-id="e1b76-230">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="e1b76-231">これにより、すべてのユーザーがストアから次のアドインを取得するのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-231">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="e1b76-232">Word、Excel、PowerPoint 2016 用のアドインは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e1b76-232">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="e1b76-233">Windows</span><span class="sxs-lookup"><span data-stu-id="e1b76-233">Windows</span></span>
    
  - <span data-ttu-id="e1b76-234">Mac</span><span class="sxs-lookup"><span data-stu-id="e1b76-234">Mac</span></span>
    
  - <span data-ttu-id="e1b76-235">Office</span><span class="sxs-lookup"><span data-stu-id="e1b76-235">Office</span></span>
    
    
- <span data-ttu-id="e1b76-236">**Appsource**内からの取得</span><span class="sxs-lookup"><span data-stu-id="e1b76-236">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="e1b76-237">Office のアドイン365</span><span class="sxs-lookup"><span data-stu-id="e1b76-237">Add-ins within Office 365</span></span>
    
<span data-ttu-id="e1b76-238">ストアにアクセスしようとするユーザーには、次のメッセージが表示されます。**申し訳ございません。 office 365 は、Office ストアアドインの個別の取得を防止するように構成されています。**</span><span class="sxs-lookup"><span data-stu-id="e1b76-238">A user who tries to access the store will see the following message: **Sorry, Office 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="e1b76-239">Office ストアの無効化のサポートは、次のバージョンで利用できます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-239">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="e1b76-240">Windows: 16.0.9001-現在使用可能です。</span><span class="sxs-lookup"><span data-stu-id="e1b76-240">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="e1b76-241">Mac: 16.10.18011401-現在利用可能です。</span><span class="sxs-lookup"><span data-stu-id="e1b76-241">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="e1b76-242">iOS: 2.9.18010804-現在使用可能です。</span><span class="sxs-lookup"><span data-stu-id="e1b76-242">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="e1b76-243">Web は現在利用できます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-243">The web - Currently available.</span></span>
    
<span data-ttu-id="e1b76-244">これにより、管理者は一元展開を使用して Office ストアからアドインを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-244">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="e1b76-245">ユーザーが Microsoft アカウントでサインインできないようにするには、組織のアカウントのみを使用するようにログオンを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-245">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="e1b76-246">詳細については、[こちら](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1b76-246">For more information, look [here](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span></span>
 
  
## <a name="minors-and-acquiring-add-ins-from-the-store"></a><span data-ttu-id="e1b76-247">未成年者とストアからのアドインの取得</span><span class="sxs-lookup"><span data-stu-id="e1b76-247">Minors and acquiring add-ins from the Store</span></span>

<span data-ttu-id="e1b76-248">一般的なデータ保護規則 (GDPR) は、2018年5月25日に有効になる欧州連合規制です。</span><span class="sxs-lookup"><span data-stu-id="e1b76-248">The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018.</span></span> <span data-ttu-id="e1b76-249">ユーザーがデータを保護するための権限が付与されます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-249">It gives users rights to and protection of their data.</span></span> <span data-ttu-id="e1b76-250">GDPR の1つの側面は、親またはガーディアンが許可されていない個人データを、未成年者が他者に送信することができないことです。</span><span class="sxs-lookup"><span data-stu-id="e1b76-250">One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved.</span></span> <span data-ttu-id="e1b76-251">マイナーとして定義された特定の年齢は、個人が配置されている地域によって異なります。</span><span class="sxs-lookup"><span data-stu-id="e1b76-251">The specific age defined as a minor depends on the region where the individual is located.</span></span>
  
<span data-ttu-id="e1b76-252">保護者の同意に関する法的な規制がある地域には、米国、南韓国、英国、および欧州連合があります。</span><span class="sxs-lookup"><span data-stu-id="e1b76-252">Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union.</span></span> <span data-ttu-id="e1b76-253">これらの地域では、マイナーがブロックされます (Azure Active Directory によって)。新しい Office アドインをストアから取得し、以前に取得したアドインを実行します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-253">For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired.</span></span> <span data-ttu-id="e1b76-254">法律上の規定がない国では、ダウンロードの制限はありません。</span><span class="sxs-lookup"><span data-stu-id="e1b76-254">For countries without statutory regulations, there will be no download restrictions.</span></span>
  
<span data-ttu-id="e1b76-255">ユーザーは、Azure Active Directory で指定されているデータに基づいて、マイナーであると判断されます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-255">A user is determined to be a minor based on data specified in Azure Active Directory.</span></span> <span data-ttu-id="e1b76-256">テナント管理者は、法務年齢グループと、そのユーザーの上位下位の同意を宣言します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-256">The tenant admin is responsible for declaring the legal age group and the parental consent for that user.</span></span>
  
<span data-ttu-id="e1b76-257">親/ガーディアンが特定のアドインを使用して小規模に同意場合は、テナント管理者は一元展開を使用して、同意を得ているすべての未成年者にそのアドインを展開できます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-257">If the parent/guardian consents to a minor using a specific add-In, then the tenant admin can use centralized deployment to deploy that add-In to all minors who have consent.</span></span>
  
<span data-ttu-id="e1b76-258">GDPR を未成年者に準拠させるには、次のいずれかの Office ビルドが学校/組織に展開されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1b76-258">To be GDPR compliant for minors you need to ensure that one of following builds of Office is deployed in your school/organization.</span></span>
  
 <span data-ttu-id="e1b76-259">**Word、Excel、PowerPoint、Project の場合**:</span><span class="sxs-lookup"><span data-stu-id="e1b76-259">**For Word, Excel, PowerPoint, and Project**:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e1b76-260">**プラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="e1b76-260">**Platform**</span></span> <br/> |<span data-ttu-id="e1b76-261">**ビルド番号**</span><span class="sxs-lookup"><span data-stu-id="e1b76-261">**Build number**</span></span> <br/> |
|<span data-ttu-id="e1b76-262">Office 2016 ProPlus 毎月 for Windows</span><span class="sxs-lookup"><span data-stu-id="e1b76-262">Office 2016 ProPlus Monthly for Windows</span></span>  <br/> |<span data-ttu-id="e1b76-263">9001.2138</span><span class="sxs-lookup"><span data-stu-id="e1b76-263">9001.2138</span></span>   <br/> |
|<span data-ttu-id="e1b76-264">Office 2016 ProPlus (半期)</span><span class="sxs-lookup"><span data-stu-id="e1b76-264">Office 2016 ProPlus Semi-Annual</span></span>  <br/> |<span data-ttu-id="e1b76-265">8431.2159</span><span class="sxs-lookup"><span data-stu-id="e1b76-265">8431.2159</span></span>  <br/> |
|<span data-ttu-id="e1b76-266">Office 2016 for Windows</span><span class="sxs-lookup"><span data-stu-id="e1b76-266">Office 2016 for Windows</span></span>  <br/> |<span data-ttu-id="e1b76-267">16.0.4672.1000</span><span class="sxs-lookup"><span data-stu-id="e1b76-267">16.0.4672.1000</span></span>  <br/> |
|<span data-ttu-id="e1b76-268">Office 2013 for Windows</span><span class="sxs-lookup"><span data-stu-id="e1b76-268">Office 2013 for Windows</span></span>  <br/> |<span data-ttu-id="e1b76-269">15.0.5023.1000</span><span class="sxs-lookup"><span data-stu-id="e1b76-269">15.0.5023.1000</span></span>  <br/> |
|<span data-ttu-id="e1b76-270">Office 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="e1b76-270">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="e1b76-271">16.11.18020200</span><span class="sxs-lookup"><span data-stu-id="e1b76-271">16.11.18020200</span></span>  <br/> |
|<span data-ttu-id="e1b76-272">Web 用 Office</span><span class="sxs-lookup"><span data-stu-id="e1b76-272">Office for the web</span></span>  <br/> |<span data-ttu-id="e1b76-273">該当なし</span><span class="sxs-lookup"><span data-stu-id="e1b76-273">N/A</span></span>  <br/> |
   
 <span data-ttu-id="e1b76-274">**Outlook の場合**:</span><span class="sxs-lookup"><span data-stu-id="e1b76-274">**For Outlook**:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e1b76-275">**プラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="e1b76-275">**Platform**</span></span> <br/> |<span data-ttu-id="e1b76-276">**ビルド番号**</span><span class="sxs-lookup"><span data-stu-id="e1b76-276">**Build number**</span></span> <br/> |
|<span data-ttu-id="e1b76-277">Outlook 2016 for Windows (MSI)</span><span class="sxs-lookup"><span data-stu-id="e1b76-277">Outlook 2016 for Windows (MSI)</span></span>  <br/> |<span data-ttu-id="e1b76-278">ビルドの未定</span><span class="sxs-lookup"><span data-stu-id="e1b76-278">Build No TBD</span></span>  <br/> |
|<span data-ttu-id="e1b76-279">Windows 版 Outlook 2016 (C2R)</span><span class="sxs-lookup"><span data-stu-id="e1b76-279">Outlook 2016 for Windows (C2R)</span></span>  <br/> |<span data-ttu-id="e1b76-280">16.0.9323.1000</span><span class="sxs-lookup"><span data-stu-id="e1b76-280">16.0.9323.1000</span></span>  <br/> |
|<span data-ttu-id="e1b76-281">Office 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="e1b76-281">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="e1b76-282">16.0.9318.1000</span><span class="sxs-lookup"><span data-stu-id="e1b76-282">16.0.9318.1000</span></span>  <br/> |
|<span data-ttu-id="e1b76-283">IOS 用の Outlook mobile</span><span class="sxs-lookup"><span data-stu-id="e1b76-283">Outlook mobile for iOS</span></span>  <br/> |<span data-ttu-id="e1b76-284">2.75.0</span><span class="sxs-lookup"><span data-stu-id="e1b76-284">2.75.0</span></span>  <br/> |
|<span data-ttu-id="e1b76-285">Outlook mobile for Android</span><span class="sxs-lookup"><span data-stu-id="e1b76-285">Outlook mobile for Android</span></span>  <br/> |<span data-ttu-id="e1b76-286">2.2.145</span><span class="sxs-lookup"><span data-stu-id="e1b76-286">2.2.145</span></span>  <br/> |
|<span data-ttu-id="e1b76-287">Outlook.com</span><span class="sxs-lookup"><span data-stu-id="e1b76-287">Outlook.com</span></span>  <br/> |<span data-ttu-id="e1b76-288">該当なし</span><span class="sxs-lookup"><span data-stu-id="e1b76-288">N/A</span></span>  <br/> |
   
 <span data-ttu-id="e1b76-289">**Office 2013 の要件**</span><span class="sxs-lookup"><span data-stu-id="e1b76-289">**Office 2013 requirements**</span></span>
  
<span data-ttu-id="e1b76-290">Windows 版 Word、Excel、PowerPoint 2013 は、Active Directory 認証ライブラリ (ADAL) が有効になっている場合と同じマイナーチェックをサポートします。</span><span class="sxs-lookup"><span data-stu-id="e1b76-290">Word, Excel, and PowerPoint 2013 for Windows will support the same minor checks if Active Directory Authentication Library (ADAL) is enabled.</span></span> <span data-ttu-id="e1b76-291">次に説明するように、2つのコンプライアンスオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="e1b76-291">There are two options for compliance, as explained next.</span></span>
  
- <span data-ttu-id="e1b76-292">**ADAL を有効に**します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-292">**Enable ADAL**.</span></span> <span data-ttu-id="e1b76-293">この記事では、office 2013 の ADAL を有効にする方法について説明します。 office [365 モダン認証を office クライアントで使用](https://support.office.com/article/776c0036-66fd-41cb-8928-5495c0f9168a)します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-293">This article explains how to enable ADAL for Office 2013: [Using Office 365 modern authentication with Office clients](https://support.office.com/article/776c0036-66fd-41cb-8928-5495c0f9168a).</span></span><br/><span data-ttu-id="e1b76-294">「 [Windows デバイスで Office 2013 の先進認証を有効](../security-and-compliance/enable-modern-authentication.md)にする」で説明されているように、レジストリキーを設定して ADAL を有効にする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="e1b76-294">You also need to set the registry keys to enable ADAL as explained in [Enable Modern Authentication for Office 2013 on Windows devices](../security-and-compliance/enable-modern-authentication.md).</span></span><br/><span data-ttu-id="e1b76-295">さらに、Office 2013 用の次の4月の更新プログラムをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1b76-295">Additionally, you need to install the following April updates for Office 2013:</span></span>
    
  - [<span data-ttu-id="e1b76-296">Office 2013 のセキュリティ更新プログラムの説明: 2018 年4月10日</span><span class="sxs-lookup"><span data-stu-id="e1b76-296">Description of the security update for Office 2013: April 10, 2018</span></span>](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [<span data-ttu-id="e1b76-297">2018年4月3日 Office 2013 の更新プログラム (KB4018333)</span><span class="sxs-lookup"><span data-stu-id="e1b76-297">April 3, 2018, update for Office 2013 (KB4018333)</span></span>](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- <span data-ttu-id="e1b76-298">**ADAL を有効にしない**でください。</span><span class="sxs-lookup"><span data-stu-id="e1b76-298">**Don't enable ADAL**.</span></span> <span data-ttu-id="e1b76-299">Office 2013 で ADAL を有効にできない場合は、グループポリシーを使用して office クライアントのストアをオフにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e1b76-299">If you're unable to enable ADAL in Office 2013, then our recommendation is to use Group Policy to turn off the Store for the office clients.</span></span> <span data-ttu-id="e1b76-300">Office 用アプリの設定を無効にする方法については、[ここ](https://technet.microsoft.com/library/cc178992.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1b76-300">Information on how to turn off the app for Office settings is located [here](https://technet.microsoft.com/library/cc178992.aspx).</span></span>
    
## <a name="end-user-experience-with-add-ins"></a><span data-ttu-id="e1b76-301">アドインのエンド ユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="e1b76-301">End user experience with add-ins</span></span>

<span data-ttu-id="e1b76-p137">アドインの展開が完了すると、エンド ユーザーは Office アプリケーションでアドインを使い始めることができます (「[Office アドインの使用を開始する](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx)」を参照)。アドインは、アドインをサポートしているすべてのプラットフォームで表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-p137">Now that you've deployed the add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx)). The add-in will appear on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="e1b76-p138">アドインがアドイン コマンドをサポートする場合、そのコマンドは Office のリボンに表示されます。次の例では、[ **引用の検索** ] コマンドが [ **引用** ] アドインで表示されています。</span><span class="sxs-lookup"><span data-stu-id="e1b76-p138">If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![検索引用を含む Office リボン](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="e1b76-307">展開されたアドインがアドインコマンドをサポートしていない場合や、展開されたすべてのアドインを表示する場合は、 **[マイ**アドイン] で表示できます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-307">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="e1b76-308">Word 2016、Excel 2016、または PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="e1b76-308">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="e1b76-309">[**マイ\>アドインの挿入**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-309">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="e1b76-310">Office アドイン ウィンドウの [ **管理による管理者** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-310">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="e1b76-311">前に展開したアドインをダブルクリックします (この例では [ **引用文献** ])。</span><span class="sxs-lookup"><span data-stu-id="e1b76-311">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="e1b76-312">![[Office アドイン] ページの [管理者による管理] タブ](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="e1b76-312">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="e1b76-313">Outlook</span><span class="sxs-lookup"><span data-stu-id="e1b76-313">In Outlook</span></span>

1. <span data-ttu-id="e1b76-314">[**ホーム**] リボンで、[アドインの**取得**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-314">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="e1b76-315">![Outlook の [格納] ボタン](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="e1b76-315">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="e1b76-316">左側のナビゲーションで、[**管理者管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-316">Select **Admin-managed** in the left nav.</span></span>

## <a name="delete-the-add-in"></a><span data-ttu-id="e1b76-317">アドインを削除する</span><span class="sxs-lookup"><span data-stu-id="e1b76-317">Delete the add-in</span></span>

<span data-ttu-id="e1b76-318">展開されたアドインを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="e1b76-318">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="e1b76-319">管理センターで、[**設定** > **サービス & アドイン**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-319">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

2. <span data-ttu-id="e1b76-320">展開されたアドインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-320">Select the deployed add-in.</span></span>

3. <span data-ttu-id="e1b76-321">[**アドインの削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1b76-321">Click on **Delete Add-In**.</span></span> <span data-ttu-id="e1b76-322">右下隅にあるアドインボタンを削除します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-322">Remove the Add-in button on the bottom right corner.</span></span>
4. <span data-ttu-id="e1b76-323">選択内容を確認し、[**アドインの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-323">Validate your selections, and choose **Remove add-in**.</span></span>
  
## <a name="learn-more"></a><span data-ttu-id="e1b76-324">詳細情報</span><span class="sxs-lookup"><span data-stu-id="e1b76-324">Learn more</span></span>

<span data-ttu-id="e1b76-325">[Office アドイン](https://go.microsoft.com/fwlink/p/?linkid=846362)の作成と構築の詳細情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-325">Learn more about creating and building [Office Add-ins](https://go.microsoft.com/fwlink/p/?linkid=846362).</span></span>
  
<span data-ttu-id="e1b76-326">[一元展開 PowerShell コマンドレットを使用してアドインを管理](https://support.office.com/article/94f4e86d-b8e5-42dd-b558-e6092f830ec9)します。</span><span class="sxs-lookup"><span data-stu-id="e1b76-326">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](https://support.office.com/article/94f4e86d-b8e5-42dd-b558-e6092f830ec9).</span></span>
  
[<span data-ttu-id="e1b76-327">トラブルシューティング: ユーザーがアドインを表示していない</span><span class="sxs-lookup"><span data-stu-id="e1b76-327">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
