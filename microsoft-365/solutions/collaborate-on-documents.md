---
title: ゲストと共同でドキュメントの作業をする
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
description: この記事では、SharePoint と OneDrive のドキュメントでゲストと共同作業する方法について説明します。
ms.openlocfilehash: 1b2fe003902b69e4c0c58852af67862ce6f2eb34
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663513"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="12b55-103">ゲストと共同でドキュメントの作業をする</span><span class="sxs-lookup"><span data-stu-id="12b55-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="12b55-104">SharePoint または OneDrive のドキュメントで組織外のユーザーと共同作業する必要がある場合は、ドキュメントへの共有リンクを送信できます。</span><span class="sxs-lookup"><span data-stu-id="12b55-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing-link to the document.</span></span> <span data-ttu-id="12b55-105">この記事では、組織のニーズに合った SharePoint と OneDrive の共有リンクを設定するために必要な Microsoft 365 構成手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="12b55-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing-links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="12b55-106">ビデオ デモンストレーション</span><span class="sxs-lookup"><span data-stu-id="12b55-106">Video demonstration</span></span>

<span data-ttu-id="12b55-107">このビデオでは、このドキュメントで説明されている構成手順を示します。</span><span class="sxs-lookup"><span data-stu-id="12b55-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="12b55-108">Azure 外部コラボレーションの設定</span><span class="sxs-lookup"><span data-stu-id="12b55-108">Azure external collaboration settings</span></span>

<span data-ttu-id="12b55-109">Microsoft 365 での共有は、Azure Active Directory の B2B 外部コラボレーション設定によって最高レベル [で管理されます](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)。</span><span class="sxs-lookup"><span data-stu-id="12b55-109">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="12b55-110">Azure AD でゲスト共有が無効または制限されている場合、この設定は Microsoft 365 で構成した共有設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="12b55-110">If guest-sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="12b55-111">B2B 外部コラボレーション設定をチェックして、ゲストとの共有がブロックされていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="12b55-111">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Azure Active Directory における組織の関係の設定ページのスクリーンショット](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="12b55-113">外部コラボレーション設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="12b55-113">To set external collaboration settings</span></span>

1. <span data-ttu-id="12b55-114">Azure Active Directory にログインします [https://aad.portal.azure.com](https://aad.portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="12b55-114">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="12b55-115">左側のナビゲーション ウィンドウで **、Azure Active Directory をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="12b55-115">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="12b55-116">[外部 **ID] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="12b55-116">Click **External identities**.</span></span>
4. <span data-ttu-id="12b55-117">[作業の **開始] 画面** の左側のナビゲーション ウィンドウで、[外部コラボレーションの設定 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="12b55-117">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="12b55-118">管理者と **ゲスト招待者の役割のユーザーが** 招待可能であり、 **メンバー** が招待可能な両方が [はい] **に設定されています**。</span><span class="sxs-lookup"><span data-stu-id="12b55-118">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="12b55-119">変更を加えた場合は、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12b55-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="12b55-120">[コラボレーションの制限] セクション **の設定に注意** してください。</span><span class="sxs-lookup"><span data-stu-id="12b55-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="12b55-121">共同作業を行うゲストのドメインがブロックされていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="12b55-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="12b55-122">複数の組織のゲストと連携する場合は、ディレクトリ データにアクセスする機能を制限できます。</span><span class="sxs-lookup"><span data-stu-id="12b55-122">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="12b55-123">これにより、他のユーザーがディレクトリのゲストであるのを見るのを防ぐのに使用できます。</span><span class="sxs-lookup"><span data-stu-id="12b55-123">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="12b55-124">これを行うには、[ゲストユーザーのアクセス制限]で、[ゲスト ユーザーがディレクトリ オブジェクトの設定のプロパティとメンバーシップに制限されたアクセス権を持っている] を選択するか、[ゲスト ユーザー アクセス] を自分のディレクトリ オブジェクトのプロパティとメンバーシップに制限 **します。**</span><span class="sxs-lookup"><span data-stu-id="12b55-124">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="12b55-125">SharePoint 組織レベルの共有設定</span><span class="sxs-lookup"><span data-stu-id="12b55-125">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="12b55-126">組織外のユーザーが SharePoint または OneDrive のドキュメントにアクセスするには、SharePoint と OneDrive の組織レベルの共有設定で組織外のユーザーとの共有を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12b55-126">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="12b55-127">SharePoint の組織レベルの設定によって、個々の SharePoint サイトで使用できる設定が決なります。</span><span class="sxs-lookup"><span data-stu-id="12b55-127">The organization-level settings for SharePoint determine the settings that will be available for individual SharePoint sites.</span></span> <span data-ttu-id="12b55-128">サイトの設定を組織レベルの設定よりも制限することはできません。</span><span class="sxs-lookup"><span data-stu-id="12b55-128">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="12b55-129">OneDrive の組織レベルの設定によって、ユーザーの OneDrive ライブラリで使用できる共有のレベルが決なります。</span><span class="sxs-lookup"><span data-stu-id="12b55-129">The organization-level setting for OneDrive determines the level of sharing that will be available in users' OneDrive libraries.</span></span>

<span data-ttu-id="12b55-130">SharePoint と OneDrive の場合、認証されていないファイルとフォルダーの共有を許可する場合は、[すべてのユーザー] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="12b55-130">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="12b55-131">組織外のユーザーが認証を行う必要がある場合は、[新規および既存のゲスト] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="12b55-131">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="12b55-132">*誰* でもリンクを共有するのが最も簡単な方法です。組織外のユーザーは認証なしでリンクを開いて、他のユーザーに自由にリンクを渡します。</span><span class="sxs-lookup"><span data-stu-id="12b55-132">*Anyone* links is the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="12b55-133">SharePoint の場合は、組織内の任意のサイトで必要になる最も制限の多い設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="12b55-133">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 組織レベルの共有設定のスクリーンショット](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="12b55-135">SharePoint 組織レベルの共有設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="12b55-135">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="12b55-136">Microsoft 365 管理センターの左側のナビゲーション ウィンドウで、[管理センター] の下の **[SharePoint] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="12b55-136">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="12b55-137">SharePoint 管理センターの左側のナビゲーション ウィンドウで、[ポリシー ] の下の [共有] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="12b55-137">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="12b55-138">SharePoint または OneDrive の外部共有が[すべてのユーザー] または [新規] および [既存のゲスト] に **設定されている必要があります**。</span><span class="sxs-lookup"><span data-stu-id="12b55-138">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="12b55-139">(OneDrive の設定は、SharePoint の設定よりも制限を制限できないことに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="12b55-139">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="12b55-140">変更を加えた場合は、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12b55-140">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="12b55-141">SharePoint 組織レベルの既定のリンク設定</span><span class="sxs-lookup"><span data-stu-id="12b55-141">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="12b55-142">既定のファイルとフォルダーのリンク設定によって、ユーザーがファイルまたはフォルダーを共有するときに既定で表示されるリンク オプションが決きます。</span><span class="sxs-lookup"><span data-stu-id="12b55-142">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="12b55-143">ユーザーは、必要に応じて、共有する前にリンクの種類を他のオプションの 1 つに変更できます。</span><span class="sxs-lookup"><span data-stu-id="12b55-143">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="12b55-144">この設定は、組織内の SharePoint サイトと OneDrive に影響を与える点に気を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="12b55-144">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="12b55-145">ユーザーがファイルやフォルダーを共有するときに既定で選択される次の種類のリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="12b55-145">Choose a link from any of the following types which is then selected by default when users share files and folders:</span></span>

- <span data-ttu-id="12b55-146">**リンクを持つすべてのユーザー** - 認証されていないファイルとフォルダーの共有を多く行う場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="12b55-146">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="12b55-147">[すべてのユーザー]リンクを許可するが、認証されていない共有の偶発的な共有を懸念している場合は、他のオプションのいずれかを既定として検討します。</span><span class="sxs-lookup"><span data-stu-id="12b55-147">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="12b55-148">このリンクの種類は、[すべてのユーザー] 共有を有効にしている場合 **にのみ使用** できます。</span><span class="sxs-lookup"><span data-stu-id="12b55-148">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="12b55-149">**組織内のユーザーのみ** - ほとんどのファイルとフォルダーの共有が組織内のユーザーと一緒に行う必要がある場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="12b55-149">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="12b55-150">**特定のユーザー** - ゲストと多くのファイルとフォルダーの共有を行う場合は、このオプションを検討してください。</span><span class="sxs-lookup"><span data-stu-id="12b55-150">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="12b55-151">この種類のリンクはゲストと一緒に機能し、認証を必要とします。</span><span class="sxs-lookup"><span data-stu-id="12b55-151">This type of link works with guests and requires them to authenticate.</span></span>
 
![SharePoint における組織レベルのファイルとフォルダー設定のスクリーンショット](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="12b55-153">SharePoint と OneDrive の組織レベルの既定のリンク設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="12b55-153">To set the SharePoint and OneDrive organization-level default link settings</span></span>

1. <span data-ttu-id="12b55-154">SharePoint 管理センターの [共有] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="12b55-154">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="12b55-155">[ **ファイルとフォルダーのリンク] で**、使用する既定の共有リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="12b55-155">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="12b55-156">変更を加えた場合は、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12b55-156">If you made changes, click **Save**.</span></span>

<span data-ttu-id="12b55-157">共有リンクのアクセス許可を設定するには、共有リンクに対して既定で選択されているアクセス許可 **を選択します。**</span><span class="sxs-lookup"><span data-stu-id="12b55-157">To set the permission for the sharing link, under **Choose the permission that's selected by default for sharing links.**</span></span>

1. <span data-ttu-id="12b55-158">認証 **されていない** ユーザーがファイルとフォルダーを変更しない場合は、[表示] を選択します。</span><span class="sxs-lookup"><span data-stu-id="12b55-158">Select **View** if you do not want unauthenticated users to make changes to the files and folders.</span></span>
2. <span data-ttu-id="12b55-159">認証 **されていない** ユーザーによるファイルとフォルダーの変更を許可する場合は、[編集] を選択します。</span><span class="sxs-lookup"><span data-stu-id="12b55-159">Select **Edit** if you want to allow unauthenticated users to make changes to the files and folders.</span></span>

<span data-ttu-id="12b55-160">上記の 2 つの事前入力オプションは、ゲスト/外部ユーザーだけでなく内部ユーザーにも適用できます。</span><span class="sxs-lookup"><span data-stu-id="12b55-160">Note that the above two premission-options can be applied not only for guests/external users but also for internal users.</span></span> <span data-ttu-id="12b55-161">選択するアクセス許可オプションは、自己判断によって決まります。</span><span class="sxs-lookup"><span data-stu-id="12b55-161">The permission-option you choose is determined by self-discretion.</span></span>

<span data-ttu-id="12b55-162">すべてのユーザーとの共有を許可するリンクのアクセス許可を設定するには</span><span class="sxs-lookup"><span data-stu-id="12b55-162">To set permissions for links that allow sharing with anyone</span></span>

1. <span data-ttu-id="12b55-163">[次 **のリンク] の下で、次のアクセス許可** を付与できます: サブウィンドウ、</span><span class="sxs-lookup"><span data-stu-id="12b55-163">Under the **These links can give these permissions:** sub-pane,</span></span> 
    1. <span data-ttu-id="12b55-164">[ **ファイル]** ドロップダウン リストから、</span><span class="sxs-lookup"><span data-stu-id="12b55-164">From the **Files** drop-down list,</span></span> 
        - <span data-ttu-id="12b55-165">認証 **されていないユーザーによる** ファイルの変更を許可する場合は、[表示と編集] を選択します。</span><span class="sxs-lookup"><span data-stu-id="12b55-165">Select **View and edit** if you want to allow unauthenticated users to make changes to the files.</span></span>
        - <span data-ttu-id="12b55-166">認証 **されていない** ユーザーがファイルを変更しない場合は、[表示] を選択します。</span><span class="sxs-lookup"><span data-stu-id="12b55-166">Select **View** if you do not want unauthenticated users to make changes to the files.</span></span>
    2. <span data-ttu-id="12b55-167">[ **フォルダー]** ドロップダウン リストから、</span><span class="sxs-lookup"><span data-stu-id="12b55-167">From the **Folders** drop-down list,</span></span>
        - <span data-ttu-id="12b55-168">認証 **されていないユーザーによるフォルダー** の変更を許可する場合は、[表示、編集、アップロード] を選択します。</span><span class="sxs-lookup"><span data-stu-id="12b55-168">Select **View, edit, and upload** if you want to allow unauthenticated users to make changes to the folders.</span></span>
        - <span data-ttu-id="12b55-169">認証 **されていない** ユーザーがフォルダーを変更しない場合は、[表示] を選択します。</span><span class="sxs-lookup"><span data-stu-id="12b55-169">Select **View** if you do not want unauthenticated users to make changes to the folders.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="12b55-170">SharePoint サイト レベルの共有設定</span><span class="sxs-lookup"><span data-stu-id="12b55-170">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="12b55-171">SharePoint サイト内のファイルとフォルダーを共有している場合は、そのサイトのサイト レベルの共有設定も確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12b55-171">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![SharePoint サイトの外部共有設定のスクリーンショット](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="12b55-173">サイト レベルの共有設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="12b55-173">To set site-level sharing settings</span></span>

1. <span data-ttu-id="12b55-174">SharePoint 管理センターの左側のナビゲーション ウィンドウで、[サイト] を展開 **し、[アクティブ** なサイト] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="12b55-174">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="12b55-175">ファイルとフォルダーをゲストと共有するサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="12b55-175">Select the site on which you want to share files and folders with guests.</span></span>
3. <span data-ttu-id="12b55-176">(選択したサイトが存在する) 行を右にスクロールし、[外部共有] 列の任意の **場所をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="12b55-176">Scroll right across the row (in which the selected site is present) and click anywhere in the **External sharing** column.</span></span>
4. <span data-ttu-id="12b55-177">表示されるページで、[ポリシー] タブ **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="12b55-177">From the page that pops up, click **Policies** tab.</span></span>
5. <span data-ttu-id="12b55-178">[外部共有 **] ウィンドウで、[** 編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="12b55-178">Under the **External sharing** pane, click **Edit**.</span></span>
6. <span data-ttu-id="12b55-179">共有が [すべてのユーザー] または [ **新規** ] および [既存の **ゲスト] に設定されている必要があります**。</span><span class="sxs-lookup"><span data-stu-id="12b55-179">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
7. <span data-ttu-id="12b55-180">変更を加えた場合は、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12b55-180">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="12b55-181">ユーザーを招待する</span><span class="sxs-lookup"><span data-stu-id="12b55-181">Invite users</span></span>

<span data-ttu-id="12b55-182">ゲスト共有の設定が構成されています。これで、ユーザーは組織外のユーザーとファイルやフォルダーを共有できます。</span><span class="sxs-lookup"><span data-stu-id="12b55-182">Guest-sharing settings are now configured; so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="12b55-183">詳細 [については、「OneDrive のファイルとフォルダーを共有](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) する [」および「SharePoint ファイルまたはフォルダー」](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12b55-183">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="12b55-184">関連項目</span><span class="sxs-lookup"><span data-stu-id="12b55-184">See also</span></span>

[<span data-ttu-id="12b55-185">認証されていないユーザーとファイルおよびフォルダーを共有するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="12b55-185">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="12b55-186">ゲストと共有するときにファイルの偶発的な公開を制限する</span><span class="sxs-lookup"><span data-stu-id="12b55-186">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="12b55-187">SharePoint と OneDrive と Azure AD B2B の統合</span><span class="sxs-lookup"><span data-stu-id="12b55-187">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
