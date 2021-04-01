---
title: 統合アプリ ポータルでパートナーによる Microsoft 365 アプリのテストと展開
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
ms.custom: AdminSurgePortfolio
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365 管理センターの統合アプリ ポータルから、組織内のユーザーおよびグループ向け Microsoft および Microsoft パートナー アプリを検索、テスト、展開します。
ms.openlocfilehash: f806d48e0ed582b1b5c1ee262058ce987125bd99
ms.sourcegitcommit: 7ebed5810480d7c49f8ca03207b5ea84993d253f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "51488291"
---
# <a name="test-and-deploy-microsoft-365-apps-by-partners-in-the-integrated-apps-portal"></a><span data-ttu-id="62853-103">統合アプリ ポータルでパートナーによる Microsoft 365 アプリのテストと展開</span><span class="sxs-lookup"><span data-stu-id="62853-103">Test and deploy Microsoft 365 Apps by partners in the Integrated apps portal</span></span>

<span data-ttu-id="62853-104">Microsoft 365 管理センターでは、1 つの場所から単一ストア アプリ、カスタム ビジネス ラインのアプリ、Microsoft 365 パートナー アプリを柔軟に展開できます。</span><span class="sxs-lookup"><span data-stu-id="62853-104">The Microsoft 365 admin center gives you the flexibility to deploy single store apps, custom business line of apps and  Microsoft 365 partner apps from a single location.</span></span> <span data-ttu-id="62853-105">場所は、Microsoft 管理センターおよび統合アプリ>設定>アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="62853-105">The location can be accessed at Microsoft Admin center > Settings > Integrated apps.</span></span> <span data-ttu-id="62853-106">統合アプリ ポータルから Microsoft パートナーが購入およびライセンスを取得したアプリを検索、テスト、および完全に展開できる機能は、ビジネス サービスを定期的に更新し、効率的に実行するために組織が必要とする利便性と利点を提供します。</span><span class="sxs-lookup"><span data-stu-id="62853-106">The ability to find, test, and fully deploy purchased and licensed apps by Microsoft partners from the Integrated apps portal provides the convenience and benefits your organization requires to keep business services updated regularly and running efficiently.</span></span>

<span data-ttu-id="62853-107">組織のパートナーからの Microsoft 365 アプリの購入とライセンスの詳細については [、「Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324)管理センターからの Microsoft 365 Apps の管理と展開」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62853-107">For additional information about purchasing and licensing Microsoft 365 apps from partners for your organization, see [Manage and deploy Microsoft 365 Apps from the Microsoft 365 admin center](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324).</span></span>

<span data-ttu-id="62853-108">パートナーがこれらのアプリを作成する方法の詳細については、「商用市場向け SaaS プランを計画する方法」 [を参照してください。](https://go.microsoft.com/fwlink/?linkid=2158277)</span><span class="sxs-lookup"><span data-stu-id="62853-108">For more info on how partners create these apps, see [How to plan a SaaS offer for the commercial marketplace](https://go.microsoft.com/fwlink/?linkid=2158277)</span></span>

<span data-ttu-id="62853-109">統合アプリ ポータルは、グローバル管理者のみアクセス可能で、WorldWide のお客様のみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="62853-109">The Integrated apps portal is only accessible to global admins and available to WorldWide customers only.</span></span> <span data-ttu-id="62853-110">この機能は、主権クラウドと政府機関クラウドでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="62853-110">This feature is not available in sovereign and government clouds.</span></span>

<span data-ttu-id="62853-111">統合アプリ ポータルには、組織に展開されているパートナーからの単一のアプリと Microsoft 365 アプリを含むアプリの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="62853-111">The Integrated apps portal displays a list of apps, which includes single apps and Microsoft 365 apps from partners which are deployed your organization.</span></span> <span data-ttu-id="62853-112">Web アプリ、SPFx アプリ、Office、Teams アプリだけが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="62853-112">Only web apps, SPFx apps, Office add-ins and Teams apps are listed.</span></span> <span data-ttu-id="62853-113">Web アプリの場合は、2 種類のアプリを確認できます。</span><span class="sxs-lookup"><span data-stu-id="62853-113">For web apps, we you can see 2 kinds of apps.</span></span>

- <span data-ttu-id="62853-114">SaaS アプリは、appsource.microsoft.com で利用可能で、組織に代わって同意を与える管理者によって展開できます。</span><span class="sxs-lookup"><span data-stu-id="62853-114">SaaS apps that are available in appsource.microsoft.com, and can be deployed by admins giving consent on behalf of organization.</span></span>
- <span data-ttu-id="62853-115">OFFICE アドインにリンクされている SAML ギャラリー アプリ。</span><span class="sxs-lookup"><span data-stu-id="62853-115">SAML gallery apps that are linked with office add-ins.</span></span>

## <a name="manage-apps-in-the-integrated-apps-portal"></a><span data-ttu-id="62853-116">統合アプリ ポータルでアプリを管理する</span><span class="sxs-lookup"><span data-stu-id="62853-116">Manage apps in the Integrated apps portal</span></span>

<span data-ttu-id="62853-117">パートナーから購入およびライセンスを取得した Microsoft 365 アプリのテストと展開を管理できます。</span><span class="sxs-lookup"><span data-stu-id="62853-117">You can manage testing and deployment of purchased and licensed Microsoft 365 Apps from partners.</span></span>

1. <span data-ttu-id="62853-118">管理センターの左側のナビゲーションで、[設定]を選択し、[統合アプリ]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="62853-118">In the admin center, in the left nav, choose **Settings**, and then choose **Integrated apps**.</span></span>

2. <span data-ttu-id="62853-119">[管理] ウィンドウを開 **くのに** 使用 **できる [** その他のアプリの状態] を含むアプリ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="62853-119">Choose an app with **Status** of **More apps available** to open the **Manage** pane.</span></span> <span data-ttu-id="62853-120">利用可能なアプリ **の** 状態を確認すると、まだ展開されていない ISV からの統合が多く存在します。</span><span class="sxs-lookup"><span data-stu-id="62853-120">The status of **more apps available** lets you know that there are more integrations from the ISVs that aren't yet deployed.</span></span>

3. <span data-ttu-id="62853-121">[概要] **タブで、[** 展開] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="62853-121">On the **Overview** tab select **Deploy**.</span></span> <span data-ttu-id="62853-122">一部のアプリでは、[展開] を選択する前にユーザーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62853-122">Some apps require you to add users before you can select Deploy.</span></span>

4. <span data-ttu-id="62853-123">[**ユーザー]** を選択し、[**この** テスト展開です]を選択し、[組織全体]、[特定の **ユーザー/グループ**]、または [自分だけ]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="62853-123">Select  **Users**, choose **Is this a test deployment**, and then choose **Entire organization**, **Specific users/groups** or **Just me**.</span></span> <span data-ttu-id="62853-124">組織全体へのアプリ **の** 展開を待機する場合は、[展開のテスト] を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="62853-124">You can also choose **Test deployment** if you prefer to wait to deploy the app to the entire organization.</span></span> <span data-ttu-id="62853-125">特定のユーザーまたはグループには、Microsoft 365 グループ、セキュリティ グループ、または配布グループを指定できます。</span><span class="sxs-lookup"><span data-stu-id="62853-125">Specific users or groups can be a Microsoft 365 group, a security group, or a distribution group.</span></span>

5. <span data-ttu-id="62853-126">[更新 **] を選択** し、[完了] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="62853-126">Select **Update** and then **Done**.</span></span> <span data-ttu-id="62853-127">[概要] タブで [展開] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="62853-127">You can now select Deploy on the Overview tab.</span></span>

6. <span data-ttu-id="62853-128">アプリ情報を確認し、[展開] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="62853-128">Review the app information, and then select **Deploy**.</span></span>

7. <span data-ttu-id="62853-129">[ **展開の** 完了] ページで [完了] を選択し、[概要] タブでテストまたは完全展開の詳細を **確認** します。</span><span class="sxs-lookup"><span data-stu-id="62853-129">Select **Done** on the Deployment completed page and review the details of the test or full deployment on the **Overview** tab.</span></span>

8. <span data-ttu-id="62853-130">アプリの状態が更新保留中の場合は、アプリをクリックして [管理] ウィンドウを開き、アプリを更新できます。</span><span class="sxs-lookup"><span data-stu-id="62853-130">If the app has a status of **Update pending**, you can click on the app to open the Manage pane and update the app.</span></span>

## <a name="find-published-apps-for-testing-and-full-deployment"></a><span data-ttu-id="62853-131">テストおよび完全展開用の公開アプリを検索する</span><span class="sxs-lookup"><span data-stu-id="62853-131">Find published apps for testing and full deployment</span></span>

<span data-ttu-id="62853-132">[統合アプリ] ページの一覧にまだ表示されない発行済みアプリを検索、テスト、および完全に展開できます。</span><span class="sxs-lookup"><span data-stu-id="62853-132">You can find, test, and fully deploy published apps that don't already appear in the list on the Integrated apps page.</span></span> <span data-ttu-id="62853-133">管理センターからアプリを購入してライセンスを取得することで、Microsoft と Microsoft のパートナー アプリを 1 つの場所からリストに追加できます。</span><span class="sxs-lookup"><span data-stu-id="62853-133">By purchasing and licensing the apps from the admin center, you can add Microsoft and Microsoft partner apps to your list from a single location.</span></span>

1. <span data-ttu-id="62853-134">管理センターの左側のナビゲーションで、[設定]を選択し、[統合アプリ]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="62853-134">In the admin center, in the left nav, choose **Settings**, and then choose **Integrated apps**.</span></span>

2. <span data-ttu-id="62853-135">[アプリ **の取得] を** 選択してアプリのビューを取得します。</span><span class="sxs-lookup"><span data-stu-id="62853-135">Select **Get apps** to get a view of the apps.</span></span>

3. <span data-ttu-id="62853-136">**[Microsoft 365 Apps 発行** アプリ] ページで、[今すぐ取得] を選択して、展開する **アプリを選択します**。</span><span class="sxs-lookup"><span data-stu-id="62853-136">On the **Microsoft 365 Apps** published apps page, select the app you want to deploy by choosing **Get it now**.</span></span> <span data-ttu-id="62853-137">主に表示されるアプリは、Word、PowerPoint、Excel、Outlook アドイン、Teams アプリ、および SharePoint アプリ (SharePoint Framework テクノロジ上に構築) です。</span><span class="sxs-lookup"><span data-stu-id="62853-137">The apps displayed primarily are Word, PowerPoint, Excel, Outlook add-ins, Teams app and SharePoint apps (built on SharePoint Framework technology).</span></span> <span data-ttu-id="62853-138">アクセス許可を受け入れ、[続行] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="62853-138">Accept the permissions and select **Continue**.</span></span>

5. <span data-ttu-id="62853-139">展開 **の** 待機を参照するメッセージの横にあるページの上部にある [展開] を選択します。</span><span class="sxs-lookup"><span data-stu-id="62853-139">Select **Deploy** at the top of the page next to the message that refers to waiting to be deployed.</span></span>

    <span data-ttu-id="62853-140">選択したアプリが ISV によって SaaS オファーにリンクされている場合、このリンクされたオファーに含まれる他のすべてのアプリが [構成] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="62853-140">If the app selected is linked to a SaaS offer by an ISV, all the other apps that are part of this linked offer will appear on the Configuration page.</span></span> <span data-ttu-id="62853-141">すべてのアプリを展開する場合は、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="62853-141">If you choose to deploy of all of the apps, select **Next**.</span></span> <span data-ttu-id="62853-142">それ以外の場合は、[ **編集] を** 選択し、展開するアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="62853-142">Otherwise, select **Edit**, and choose which apps you want deployed.</span></span> <span data-ttu-id="62853-143">一部のアプリでは、[展開] を選択する前にユーザーを追加する **必要があります**。</span><span class="sxs-lookup"><span data-stu-id="62853-143">Some apps require you to add users before you can select **Deploy**.</span></span>

6. <span data-ttu-id="62853-144">[**ユーザーの追加]** を選択し、[**この** テスト展開です] を選択し、[組織全体] または [特定のユーザー **/グループ**] または [自分だけ]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="62853-144">Select **Add users**, choose **Is this a test deployment**, and then choose **Entire organization** or **Specific users/groups** or **Just me**.</span></span>

    <span data-ttu-id="62853-145">特定のユーザー/グループには、Microsoft 365 グループ、セキュリティ グループ、または分散グループを指定できます。</span><span class="sxs-lookup"><span data-stu-id="62853-145">Specific users/groups can be a Microsoft 365 group, a security group, or a distributed group.</span></span> <span data-ttu-id="62853-146">組織全体へのアプリ **の** 展開を待機する場合は、[展開のテスト] を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="62853-146">You can also choose **Test deployment** if you prefer to wait to deploy the app to the entire organization.</span></span>

7. <span data-ttu-id="62853-147">[ **次へ]** を選択して 、[アクセス許可の **要求を受け入れる] ページに移動** します。</span><span class="sxs-lookup"><span data-stu-id="62853-147">Select **Next** to get to the **Accept permission request** page.</span></span> <span data-ttu-id="62853-148">各アプリのアプリ機能とアクセス許可が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="62853-148">The app capabilities and permissions of each of the apps are listed.</span></span> <span data-ttu-id="62853-149">アプリで同意が必要な場合は、[アクセス許可を **受け入れる] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="62853-149">If the app needs consent, select **Accept permissions**.</span></span> <span data-ttu-id="62853-150">同意できるのは、グローバル管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="62853-150">Only a global administrator can give consent.</span></span>

8. <span data-ttu-id="62853-151">[次 **へ] を** 選択して展開を確認し、[展開の完了 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="62853-151">Select **Next** to review the deployment and choose **Finish deployment**.</span></span> <span data-ttu-id="62853-152">[この展開を表示する] **を選択すると** 、[概要] タブ **から展開を表示できます**。</span><span class="sxs-lookup"><span data-stu-id="62853-152">You can view the deployment from the **Overview** tab by choosing **View this deployment**.</span></span> <span data-ttu-id="62853-153">Microsoft 365 管理センターでは、展開された各アプリの状態と、アプリを展開した日付を確認できます。</span><span class="sxs-lookup"><span data-stu-id="62853-153">In the Microsoft 365 admin center, you can see the status of each deployed app and the date you deployed the app.</span></span>

> [!NOTE]
> <span data-ttu-id="62853-154">アプリが統合アプリ ポータル以外の場所から以前に展開された場合、展開の種類 **はカスタム\*\*\*\*です。**</span><span class="sxs-lookup"><span data-stu-id="62853-154">If an app was previously deployed from somewhere other than the Integrated Apps portal, the **Deployment Type** is **Custom.**</span></span>

## <a name="unsupported-scenarios"></a><span data-ttu-id="62853-155">サポートされていないシナリオ</span><span class="sxs-lookup"><span data-stu-id="62853-155">Unsupported scenarios</span></span>

<span data-ttu-id="62853-156">次のシナリオでは、統合アプリ ポータルからパートナー別に 1 つのストア アプリまたは Microsoft 365 アプリを展開できません。</span><span class="sxs-lookup"><span data-stu-id="62853-156">You won't be able to deploy a single store app or Microsoft 365 Apps by partner from Integrated apps portal for the following scenarios.</span></span>

- <span data-ttu-id="62853-157">同じアドインが複数の SaaS オファーにリンクされています。</span><span class="sxs-lookup"><span data-stu-id="62853-157">The same add-in is linked to more than one SaaS offer.</span></span>
- <span data-ttu-id="62853-158">SaaS オファーはアドインにリンクされますが、Microsoft Graph と統合されるのではなく、AAD アプリ ID は提供されない。</span><span class="sxs-lookup"><span data-stu-id="62853-158">The SaaS offer is linked to add-ins, but it does not integrate with Microsoft Graph and no AAD App ID is provided.</span></span>
- <span data-ttu-id="62853-159">SaaS オファーはアドインにリンクされますが、Microsoft Graph 統合用に提供される AAD アプリ ID は複数の SaaS オファー間で共有されます。</span><span class="sxs-lookup"><span data-stu-id="62853-159">The SaaS offer is linked to add-ins, but AAD App ID provided for Microsoft Graph integration is shared across multiple SaaS offers.</span></span>

## <a name="upload-custom-line-of-business-apps-for-testing-and-full-deployment"></a><span data-ttu-id="62853-160">テストと完全展開用にカスタム のビジネス アプリをアップロードする</span><span class="sxs-lookup"><span data-stu-id="62853-160">Upload custom line of business apps for testing and full deployment</span></span>

1. <span data-ttu-id="62853-161">管理センターの左側のナビゲーションで、[設定] を選択 **し、[統合** アプリ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="62853-161">In the admin center, in the left nav, choose **Settings** and then **Integrated apps**.</span></span>

2. <span data-ttu-id="62853-162">[カスタム **アプリのアップロード] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="62853-162">Select **Upload custom apps**.</span></span> <span data-ttu-id="62853-163">Word、PowerPoint、Excel、および Outlook 用のアプリのカスタム 行だけがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="62853-163">Only a custom line of apps for Word, PowerPoint, Excel and Outlook  is supported.</span></span>

3. <span data-ttu-id="62853-164">デバイスからマニフェスト ファイルをアップロードするか、URL リンクを追加します。</span><span class="sxs-lookup"><span data-stu-id="62853-164">Upload the manifest file from your device or add a URL link.</span></span> <span data-ttu-id="62853-165">一部のアプリでは、[展開] を選択する前にユーザーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62853-165">Some apps require you to add users before you can select Deploy.</span></span>

4. <span data-ttu-id="62853-166">[**ユーザーの追加]** を選択し、[**これは** テスト展開です] を選択し、[組織全体] または [特定のユーザー **/グループ**] または [自分だけ]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="62853-166">Select **Add users**, choose **Is this a test Deployment**, and choose **Entire organization** or **Specific users/groups** or **Just me**.</span></span>

    <span data-ttu-id="62853-167">特定のユーザー/グループには、Microsoft 365 グループ、セキュリティ グループ、または分散グループを指定できます。</span><span class="sxs-lookup"><span data-stu-id="62853-167">Specific users/groups can be a Microsoft 365 group, a security group, or a distributed group.</span></span> <span data-ttu-id="62853-168">組織全体へのアプリ **の** 展開を待機する場合は、[展開のテスト] を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="62853-168">You can also choose **Test deployment** if you want to wait to deploy the app to the entire organization.</span></span>

5. <span data-ttu-id="62853-169">[ **次へ]** を選択して 、[アクセス許可の **要求を受け入れる] ページに移動** します。</span><span class="sxs-lookup"><span data-stu-id="62853-169">Select **Next** to get to the **Accept permission request** page.</span></span> <span data-ttu-id="62853-170">アプリの機能とアクセス許可が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="62853-170">The app capabilities and permissions of the apps are listed.</span></span> <span data-ttu-id="62853-171">アプリで同意が必要な場合は、[アクセス許可を **受け入れる] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="62853-171">If the app needs consent, select **Accept permissions**.</span></span> <span data-ttu-id="62853-172">同意できるのは、グローバル管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="62853-172">Only a global administrator can give consent.</span></span>

6. <span data-ttu-id="62853-173">[次 **へ] を** 選択して展開を確認し、[展開の完了 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="62853-173">Select **Next** to review the deployment and choose **Finish deployment**.</span></span> <span data-ttu-id="62853-174">[この展開を表示する] **を選択すると** 、[概要] タブ **から展開を表示できます**。</span><span class="sxs-lookup"><span data-stu-id="62853-174">You can view the deployment from the **Overview** tab by choosing **View this deployment**.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="62853-175">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="62853-175">Frequently asked questions</span></span>

### <a name="which-administrator-role-do-i-need-to-access-integrated-apps"></a><span data-ttu-id="62853-176">統合アプリにアクセスする必要がある管理者の役割</span><span class="sxs-lookup"><span data-stu-id="62853-176">Which administrator role do I need to access Integrated apps?</span></span>

<span data-ttu-id="62853-177">統合アプリにアクセスできるのは、グローバル管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="62853-177">Only global administrators can access Integrated Apps.</span></span> <span data-ttu-id="62853-178">統合アプリは、他の管理者の左側のナビゲーションには表示されません。</span><span class="sxs-lookup"><span data-stu-id="62853-178">Integrated apps won't show up in the left nav for other administrators.</span></span>

### <a name="why-do-i-see-add-in-in-the-left-nav-under-setting-but-not-integrated-apps"></a><span data-ttu-id="62853-179">[設定] の下の左側のナビゲーションにアドインが表示されますが、統合アプリは表示されません。</span><span class="sxs-lookup"><span data-stu-id="62853-179">Why do I see Add-in in the left nav under Setting but not Integrated apps?</span></span>

<span data-ttu-id="62853-180">いくつかの理由があります。</span><span class="sxs-lookup"><span data-stu-id="62853-180">There could be a few reasons:</span></span>

- <span data-ttu-id="62853-181">ログインしている管理者は Exchange admininstrator です。</span><span class="sxs-lookup"><span data-stu-id="62853-181">The logged in administrator is an Exchange admininstrator.</span></span>
- <span data-ttu-id="62853-182">顧客はソブリン クラウドに入っていますが、統合アプリ エクスペリエンスは、ソブリン クラウドのお客様が利用できます。</span><span class="sxs-lookup"><span data-stu-id="62853-182">The customer is in sovereign cloud and Integrated apps experience is available to sovereign cloud customers yet.</span></span>

### <a name="what-apps-can-i-deploy-from-integrated-apps"></a><span data-ttu-id="62853-183">統合アプリから展開できるアプリ</span><span class="sxs-lookup"><span data-stu-id="62853-183">What apps can I deploy from Integrated apps?</span></span>

<span data-ttu-id="62853-184">統合アプリを使用すると、Web アプリ、Teams アプリ、Excel、PowerPoint、Word、Outlook アドイン、SPFx アプリを展開できます。</span><span class="sxs-lookup"><span data-stu-id="62853-184">Integrated apps allows deployment of Web Apps, Teams app, Excel, PowerPoint, Word, Outlook add-ins, and SPFx apps.</span></span> <span data-ttu-id="62853-185">アドインの場合、統合アプリは、オンプレミスの Exchange メールボックスではなく、Exchange オンライン メールボックスへの展開をサポートします。</span><span class="sxs-lookup"><span data-stu-id="62853-185">For add-ins, Integrated apps supports deployment to Exchange online mailboxes and not on-premises Exchange mailboxes.</span></span>

### <a name="can-administrators-delete-or-remove-apps"></a><span data-ttu-id="62853-186">管理者はアプリを削除または削除できますか?</span><span class="sxs-lookup"><span data-stu-id="62853-186">Can administrators delete or remove apps?</span></span>

<span data-ttu-id="62853-187">はい。</span><span class="sxs-lookup"><span data-stu-id="62853-187">Yes.</span></span> <span data-ttu-id="62853-188">グローバル管理者は、アプリを削除または削除できます。</span><span class="sxs-lookup"><span data-stu-id="62853-188">Global administrators can delete or remove apps.</span></span>

- <span data-ttu-id="62853-189">リスト ビューからアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="62853-189">Select an app from the list view.</span></span> <span data-ttu-id="62853-190">[構成 **] タブ** で、削除するアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="62853-190">On the **Configuration** tab, select which apps to remove.</span></span>  

### <a name="is-integrated-apps-available-in-sovereign-cloud"></a><span data-ttu-id="62853-191">統合アプリはソブリン クラウドで利用できますか?</span><span class="sxs-lookup"><span data-stu-id="62853-191">Is Integrated apps available in sovereign cloud?</span></span>

<span data-ttu-id="62853-192">いいえ。</span><span class="sxs-lookup"><span data-stu-id="62853-192">No.</span></span> <span data-ttu-id="62853-193">統合アプリは、ソブリン クラウドのお客様が利用できません。</span><span class="sxs-lookup"><span data-stu-id="62853-193">Integrated apps aren't available to sovereign cloud customers.</span></span>

### <a name="is-integrated-apps-available-in-government-clouds"></a><span data-ttu-id="62853-194">統合アプリは政府機関のクラウドで利用できますか?</span><span class="sxs-lookup"><span data-stu-id="62853-194">Is Integrated apps available in government clouds?</span></span>

<span data-ttu-id="62853-195">いいえ。</span><span class="sxs-lookup"><span data-stu-id="62853-195">No.</span></span> <span data-ttu-id="62853-196">統合アプリは、政府機関のクラウド顧客が利用できません。</span><span class="sxs-lookup"><span data-stu-id="62853-196">Integrated apps aren't available to government cloud customers.</span></span>
