---
title: サイトでゲストと共同で作業する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: ゲストとの共同作業用に SharePoint サイトをセットアップするために必要な Microsoft 365 構成手順について説明します。
ms.openlocfilehash: 6862fe715fe2f19b968b773bc6df6c70c207a44f
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663526"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="3c0c6-103">サイトでゲストと共同で作業する</span><span class="sxs-lookup"><span data-stu-id="3c0c6-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="3c0c6-104">ドキュメント、データ、およびリスト間でゲストと共同作業する必要がある場合は、SharePoint サイトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="3c0c6-105">最新の SharePoint サイトは Microsoft 365 グループに接続され、サイト メンバーシップを管理し、共有メールボックスや予定表などの追加のコラボレーション ツールを提供できます。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and a calendar.</span></span>

<span data-ttu-id="3c0c6-106">この記事では、ゲストとの共同作業用に SharePoint サイトをセットアップするために必要な Microsoft 365 構成手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="3c0c6-107">ビデオ デモンストレーション</span><span class="sxs-lookup"><span data-stu-id="3c0c6-107">Video demonstration</span></span>

<span data-ttu-id="3c0c6-108">このビデオでは、このドキュメントで説明されている構成手順を示します。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="3c0c6-109">Azure 外部コラボレーションの設定</span><span class="sxs-lookup"><span data-stu-id="3c0c6-109">Azure external collaboration settings</span></span>

<span data-ttu-id="3c0c6-110">Microsoft 365 での共有は、Azure Active Directory の B2B 外部コラボレーション設定によって最高レベル [で管理されます](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-110">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="3c0c6-111">Azure AD でゲスト共有が無効または制限されている場合、この設定は Microsoft 365 で構成した共有設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="3c0c6-112">B2B 外部コラボレーション設定を確認して、ゲストとの共有がブロックされていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-112">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![[Azure Active Directory 外部コラボレーションの設定] ページのスクリーンショット](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="3c0c6-114">外部コラボレーション設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="3c0c6-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="3c0c6-115">Azure Active Directory にログインします [https://aad.portal.azure.com](https://aad.portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="3c0c6-116">左側のナビゲーション ウィンドウで **、Azure Active Directory をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="3c0c6-117">[外部 **ID] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-117">Click **External identities**.</span></span>
4. <span data-ttu-id="3c0c6-118">[作業の **開始] 画面** の左側のナビゲーション ウィンドウで、[外部コラボレーションの設定 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="3c0c6-119">管理者と **ゲスト招待者の役割のユーザーが** 招待可能であり、 **メンバー** が招待可能な両方が [はい] **に設定されています**。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="3c0c6-120">変更を加えた場合は、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="3c0c6-121">[コラボレーションの制限] セクション **の設定に注意** してください。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="3c0c6-122">共同作業を行うゲストのドメインがブロックされていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="3c0c6-123">複数の組織のゲストと連携する場合は、ディレクトリ データにアクセスする機能を制限できます。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="3c0c6-124">これにより、他のユーザーがディレクトリのゲストであるのを見るのを防ぐのに使用できます。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="3c0c6-125">これを行うには、[ゲストユーザーのアクセス制限]で、[ゲスト ユーザーがプロパティへのアクセス権とディレクトリ オブジェクト設定のメンバーシップに制限されている] を選択するか、[ゲスト **ユーザー** アクセス] を自分のディレクトリ オブジェクトのプロパティとメンバーシップに制限します。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="3c0c6-126">Microsoft 365 グループのゲスト設定</span><span class="sxs-lookup"><span data-stu-id="3c0c6-126">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="3c0c6-127">モダン SharePoint サイトでは、Microsoft 365 グループを使用してサイトアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-127">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="3c0c6-128">SharePoint サイトでゲスト アクセスを機能するには、Microsoft 365 グループのゲスト設定を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-128">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Microsoft 365 管理センターにおける Microsoft 365 グループのゲスト設定のスクリーンショット](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="3c0c6-130">Microsoft 365 グループのゲスト設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="3c0c6-130">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="3c0c6-131">Microsoft 365 管理センターの左側のナビゲーション ウィンドウで、[設定] を **展開します**。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-131">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="3c0c6-132">[ **組織の設定] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-132">Click **Org settings**.</span></span>
3. <span data-ttu-id="3c0c6-133">一覧で **、[Microsoft 365 グループ] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-133">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="3c0c6-134">[グループ所有者が組織外のユーザーをゲストとして **Microsoft 365 グループ** に追加する] チェック ボックスと [ゲスト グループ のメンバーがグループ コンテンツにアクセスする] の両方のチェック ボックスがオンになっています。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-134">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="3c0c6-135">変更を加えた場合は、[変更の保存] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-135">If you made changes, click **Save changes**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="3c0c6-136">SharePoint 組織レベルの共有設定</span><span class="sxs-lookup"><span data-stu-id="3c0c6-136">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="3c0c6-137">ゲストが SharePoint サイトにアクセスするには、SharePoint 組織レベルの共有設定でゲストとの共有を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-137">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="3c0c6-138">組織レベルの設定によって、個々のサイトで使用できる設定が決なります。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-138">The organization-level settings determine the settings that will be available for individual sites.</span></span> <span data-ttu-id="3c0c6-139">サイトの設定を組織レベルの設定よりも制限することはできません。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-139">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="3c0c6-140">認証されていないファイルとフォルダーの共有を許可する場合は、[すべてのユーザー] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-140">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="3c0c6-141">組織外のすべてのユーザーが認証を行う必要がある場合は、[新規および既存のゲスト] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-141">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="3c0c6-142">組織内の任意のサイトで必要になる最も制限の多い設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-142">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 組織レベルの共有設定のスクリーンショット](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="3c0c6-144">SharePoint 組織レベルの共有設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="3c0c6-144">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="3c0c6-145">Microsoft 365 管理センターの左側のナビゲーション ウィンドウで、[管理センター] の下の **[SharePoint] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-145">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="3c0c6-146">SharePoint 管理センターの左側のナビゲーション ウィンドウで、[ポリシー ] の下の [共有] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-146">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="3c0c6-147">SharePoint の外部共有が [すべてのユーザー] または [新規] および [既存の **ゲスト] に設定されている必要があります**。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-147">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="3c0c6-148">変更を加えた場合は、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-148">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="3c0c6-149">サイトを作成する</span><span class="sxs-lookup"><span data-stu-id="3c0c6-149">Create a site</span></span>

<span data-ttu-id="3c0c6-150">次の手順では、ゲストとの共同作業に使用する予定のサイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-150">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="3c0c6-151">サイトを作成するには</span><span class="sxs-lookup"><span data-stu-id="3c0c6-151">To create a site</span></span>
1. <span data-ttu-id="3c0c6-152">SharePoint 管理センターで、**[サイト]** の下側にある **[アクティブなサイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-152">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="3c0c6-153">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-153">Click **Create**.</span></span>
3. <span data-ttu-id="3c0c6-154">[チーム **サイト] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-154">Click **Team site**.</span></span>
4. <span data-ttu-id="3c0c6-155">サイト名を入力し、グループ所有者 (サイト所有者) の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-155">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="3c0c6-156">[ **詳細設定] で**、このサイトをパブリックサイトにするか、プライベートサイトにするか選択します。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-156">Under **Advanced settings**, choose if you want this site to be a public or private one.</span></span>
6. <span data-ttu-id="3c0c6-157">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-157">Click **Next**.</span></span>
7. <span data-ttu-id="3c0c6-158">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-158">Click **Finish**.</span></span>

<span data-ttu-id="3c0c6-159">後でユーザーを招待します。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-159">We'll invite users later.</span></span> <span data-ttu-id="3c0c6-160">次に、このサイトのサイト レベルの共有設定を確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-160">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="3c0c6-161">SharePoint サイト レベルの共有設定</span><span class="sxs-lookup"><span data-stu-id="3c0c6-161">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="3c0c6-162">サイト レベルの共有設定を確認して、このサイトに必要なアクセスの種類を許可します。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-162">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="3c0c6-163">たとえば、組織レベルの設定を **[** すべてのユーザー] に設定し、すべてのゲストに対してこのサイトの認証を行う場合は、サイト レベルの共有設定が [新規] および [既存のゲスト] に設定されている必要 **があります。**</span><span class="sxs-lookup"><span data-stu-id="3c0c6-163">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="3c0c6-164">サイトを認証されていないユーザー **([** すべてのユーザー] 設定) と共有することはできませんが、個々のファイルとフォルダーは共有できます。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-164">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

<span data-ttu-id="3c0c6-165">また、SharePoint サイト [の外部共有設定を制御するために、区別ラベルを使用することもできます](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-165">You can also use [sensitivity labels to control external sharing settings for SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

![SharePoint サイトの外部共有設定のスクリーンショット](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="3c0c6-167">サイト レベルの共有設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="3c0c6-167">To set site-level sharing settings</span></span>
1. <span data-ttu-id="3c0c6-168">SharePoint 管理センターの左側のナビゲーションで、[**サイト**] を展開して [**アクティブなサイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-168">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="3c0c6-169">共有するサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-169">Select the site that you want to share.</span></span>
3. <span data-ttu-id="3c0c6-170">[...] をクリックし、[共有] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-170">Click ..., and click **Sharing**.</span></span>
4. <span data-ttu-id="3c0c6-171">共有が [すべてのユーザー] または **[新規** ] および [ **既存のゲスト] に設定されている必要があります**。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-171">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="3c0c6-172">変更を加えた場合は、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-172">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="3c0c6-173">ユーザーを招待する</span><span class="sxs-lookup"><span data-stu-id="3c0c6-173">Invite users</span></span>

<span data-ttu-id="3c0c6-174">ゲスト共有設定が構成されたので、内部ユーザーとゲストをサイトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-174">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="3c0c6-175">サイト アクセスは、関連付けられた Microsoft 365 グループを通じて制御されます。そのため、そこにユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-175">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="3c0c6-176">内部ユーザーをグループに招待するには</span><span class="sxs-lookup"><span data-stu-id="3c0c6-176">To invite internal users to a group</span></span>
1. <span data-ttu-id="3c0c6-177">ユーザーを追加するサイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-177">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="3c0c6-178">右上 **の** [メンバー] リンク (メンバー数を示す) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-178">Click **Members** link in the upper right which denotes the member count.</span></span>
3. <span data-ttu-id="3c0c6-179">**[メンバーの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-179">Click **Add members**.</span></span>
4. <span data-ttu-id="3c0c6-180">サイトに招待するユーザーの名前または電子メール アドレスを入力し、[保存] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-180">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="3c0c6-181">ゲストをサイトから追加できない。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-181">Guests can't be added from the site.</span></span> <span data-ttu-id="3c0c6-182">Outlook on the web を使用して追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-182">You need to add them using Outlook on the web.</span></span> <span data-ttu-id="3c0c6-183">そのため、ゲストを追加してグループに招待する前提条件として、[URL] 列でサイトの URLをクリックして、サイト固有のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-183">Therefore, as a prerequisite to add and invite guests to a group, click the URL of the site in the **URL**  column to navigate to the site-specific page.</span></span> <span data-ttu-id="3c0c6-184">このページで、[アプリ起動ツール] アイコン **を** クリックし **、[Outlook] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-184">From this page, click the **App launcher** icon and select **Outlook**.</span></span> <span data-ttu-id="3c0c6-185">これは、グループにゲストを招待できる画面で、以下に示す手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-185">This is the screen from which you can invite guests into a group, for which procedure is described below.</span></span>

<span data-ttu-id="3c0c6-186">ゲストをグループに招待するには</span><span class="sxs-lookup"><span data-stu-id="3c0c6-186">To invite guests to a group</span></span>
1. <span data-ttu-id="3c0c6-187">[ **グループ]** で、ゲストを招待するグループをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-187">Under **Groups**, click the group to which you want to invite guests.</span></span>
2. <span data-ttu-id="3c0c6-188">グループ連絡先カードを開き、右上の [メンバー] リンク (メンバー数を示すリンク) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-188">Open the group contact card, click **Members** link in the upper right (the link which denotes the member count).</span></span>
3. <span data-ttu-id="3c0c6-189">[メンバー **の追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-189">click **Add members**.</span></span>
4. <span data-ttu-id="3c0c6-190">招待するゲストのメール アドレスを入力し、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-190">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
5. <span data-ttu-id="3c0c6-191">[閉じる] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-191">Click **Close**.</span></span>
<span data-ttu-id="3c0c6-192">[閉じる] をクリックする必要があるのは、ユーザーがグループの所有者ではなく、その結果、グループにゲストを追加できない場合のみです。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-192">Note that you need to click **Close** only if you are not the owner of the group and as a result, you are not allowed to add the guest into the group.</span></span> <span data-ttu-id="3c0c6-193">このような場合、グループにゲストを追加する要求は、承認のためにグループの所有者に転送されます。</span><span class="sxs-lookup"><span data-stu-id="3c0c6-193">In such cases, the request to add the guest into the group is transferred to the group owner for approval.</span></span>

## <a name="see-also"></a><span data-ttu-id="3c0c6-194">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c0c6-194">See also</span></span>

[<span data-ttu-id="3c0c6-195">認証されていないユーザーとファイルおよびフォルダーを共有するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="3c0c6-195">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="3c0c6-196">ゲストと共有するときにファイルの偶発的な公開を制限する</span><span class="sxs-lookup"><span data-stu-id="3c0c6-196">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="3c0c6-197">セキュリティで保護されたゲスト共有環境を作成する</span><span class="sxs-lookup"><span data-stu-id="3c0c6-197">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="3c0c6-198">管理されたゲストで B2B エクストラネットを作成する</span><span class="sxs-lookup"><span data-stu-id="3c0c6-198">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="3c0c6-199">SharePoint と OneDrive と Azure AD B2B の統合</span><span class="sxs-lookup"><span data-stu-id="3c0c6-199">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
