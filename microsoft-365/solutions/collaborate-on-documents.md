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
recommendations: false
description: この記事では、ドキュメントのゲストと共同作業を行う方法について、SharePointおよびOneDrive。
ms.openlocfilehash: 338c7f32944bccb766ed923c12a9fceee4d81db8
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537837"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="0296c-103">ゲストと共同でドキュメントの作業をする</span><span class="sxs-lookup"><span data-stu-id="0296c-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="0296c-104">SharePoint または OneDrive のドキュメントで組織外のユーザーと共同作業する必要がある場合は、共有リンクをドキュメントに送信できます。</span><span class="sxs-lookup"><span data-stu-id="0296c-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing-link to the document.</span></span> <span data-ttu-id="0296c-105">この記事では、組織のニーズに合った SharePoint と OneDrive の共有リンクを設定するために必要な Microsoft 365 構成手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="0296c-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing-links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="0296c-106">ビデオ デモンストレーション</span><span class="sxs-lookup"><span data-stu-id="0296c-106">Video demonstration</span></span>

<span data-ttu-id="0296c-107">このビデオは、このドキュメントで説明されている構成手順を示しています。</span><span class="sxs-lookup"><span data-stu-id="0296c-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="0296c-108">Azure の外部コラボレーション設定</span><span class="sxs-lookup"><span data-stu-id="0296c-108">Azure external collaboration settings</span></span>

<span data-ttu-id="0296c-109">Microsoft 365 での共有は、[Azure Active Directory における B2B 外部コラボレーションの設定](/azure/active-directory/external-identities/delegate-invitations) によって最高レベルで管理されます。</span><span class="sxs-lookup"><span data-stu-id="0296c-109">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="0296c-110">Azure AD でゲスト共有が無効または制限されている場合、この設定は、ユーザー設定で構成する共有設定Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="0296c-110">If guest-sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="0296c-111">B2B 外部コラボレーション設定を確認して、ゲストとの共有がブロックされないか確認します。</span><span class="sxs-lookup"><span data-stu-id="0296c-111">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Azure Active Directory における組織関係の設定ページのスクリーンショット](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="0296c-113">外部コラボレーションを設定するには</span><span class="sxs-lookup"><span data-stu-id="0296c-113">To set external collaboration settings</span></span>

1. <span data-ttu-id="0296c-114">[https://aad.portal.azure.com](https://aad.portal.azure.com) で Azure Active Directory にログインします。</span><span class="sxs-lookup"><span data-stu-id="0296c-114">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="0296c-115">左側のナビゲーション ウィンドウで **[Azure Active Directory]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0296c-115">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="0296c-116">**[外部 ID]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0296c-116">Click **External identities**.</span></span>
4. <span data-ttu-id="0296c-117">**[開始]** 画面で、左側のナビゲーション ウィンドウで **[外部コラボレーション設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0296c-117">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="0296c-118">**[管理者とゲスト招待者の役割のユーザーが招待できる]** と **[メンバーが招待できる]** を両方とも **[はい]** に設定していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0296c-118">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="0296c-119">変更を加えた場合は、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0296c-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="0296c-120">**[共同作業の制限]** セクションの設定に注意してください。</span><span class="sxs-lookup"><span data-stu-id="0296c-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="0296c-121">共同作業するゲストのドメインがブロックされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="0296c-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="0296c-122">複数の組織のゲストと連携する場合は、ディレクトリ データにアクセスするゲストの機能を制限することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0296c-122">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="0296c-123">これにより、他に誰がディレクトリ内のゲストであるかを確認できなくなります。</span><span class="sxs-lookup"><span data-stu-id="0296c-123">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="0296c-124">これを行うには、**[ゲスト ユーザーのアクセス制限]** で、**[ゲスト ユーザーはディレクトリ オブジェクト設定のプロパティとメンバーシップに制限付きアクセス権が付与されている]** または **[ゲスト ユーザーのアクセスは自分のディレクトリ オブジェクトのプロパティとメンバーシップに制限されている]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0296c-124">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="0296c-125">SharePointレベルの共有設定</span><span class="sxs-lookup"><span data-stu-id="0296c-125">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="0296c-126">組織外のユーザーが SharePoint または OneDrive のドキュメントにアクセスするには、SharePoint と OneDrive の組織レベルの共有設定で組織外のユーザーとの共有を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0296c-126">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="0296c-127">組織レベルの設定は、SharePointサイトで使用できる設定をSharePointします。</span><span class="sxs-lookup"><span data-stu-id="0296c-127">The organization-level settings for SharePoint determine the settings that will be available for individual SharePoint sites.</span></span> <span data-ttu-id="0296c-128">サイトの設定は、組織レベルの設定よりも制限を緩和することはできません。</span><span class="sxs-lookup"><span data-stu-id="0296c-128">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="0296c-129">ユーザーの組織レベルの設定OneDrive、ユーザーの共有ライブラリで使用できる共有のOneDriveします。</span><span class="sxs-lookup"><span data-stu-id="0296c-129">The organization-level setting for OneDrive determines the level of sharing that will be available in users' OneDrive libraries.</span></span>

<span data-ttu-id="0296c-130">[SharePointとOneDrive、認証されていないファイルとフォルダーの共有を許可する場合は、[すべてのユーザー] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="0296c-130">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="0296c-131">組織外のユーザーが認証する必要がある場合は、[新規ゲストと既存のゲスト] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0296c-131">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="0296c-132">*誰* でもリンクを共有するのが最も簡単な方法です。組織外のユーザーは、認証なしでリンクを開き、それを他のユーザーに自由に渡します。</span><span class="sxs-lookup"><span data-stu-id="0296c-132">*Anyone* links is the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="0296c-133">たとえばSharePoint、組織内の任意のサイトで必要になる最も制限の多い設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="0296c-133">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 組織レベルの共有設定のスクリーンショット](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="0296c-135">SharePoint 組織レベルの共有設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="0296c-135">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="0296c-136">Microsoft 365 管理センターの左側のナビゲーション ウィンドウの **[管理センター]** で、**[SharePoint]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0296c-136">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="0296c-137">管理センター SharePoint左側のナビゲーション ウィンドウの [ポリシー] で、[**共有]** を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="0296c-137">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="0296c-138">ユーザーまたはユーザーの外部SharePoint共有OneDrive[すべてのユーザー] または [新しいゲストと既存のゲスト **] に設定します**。</span><span class="sxs-lookup"><span data-stu-id="0296c-138">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="0296c-139">(この設定は、OneDriveの設定よりもSharePoint注意してください。</span><span class="sxs-lookup"><span data-stu-id="0296c-139">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="0296c-140">変更を加えた場合は、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0296c-140">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="0296c-141">SharePoint 組織レベルの既定のリンク設定</span><span class="sxs-lookup"><span data-stu-id="0296c-141">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="0296c-142">既定のファイルとフォルダーのリンク設定により、ファイルまたはフォルダーを共有するときに既定でユーザーに表示されるリンク オプションが決まります。</span><span class="sxs-lookup"><span data-stu-id="0296c-142">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="0296c-143">ユーザーは、必要に応じて、共有する前に他のオプションのいずれかにリンクの種類を変更できます。</span><span class="sxs-lookup"><span data-stu-id="0296c-143">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="0296c-144">この設定は、組織SharePointサイトに影響を及ぼすOneDrive。</span><span class="sxs-lookup"><span data-stu-id="0296c-144">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="0296c-145">ユーザーがファイルとフォルダーを共有するときに既定で選択される次の種類のリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="0296c-145">Choose a link from any of the following types which is then selected by default when users share files and folders:</span></span>

- <span data-ttu-id="0296c-146">**リンクを持つユーザー** - 認証されていないファイルとフォルダー共有を多く行う場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0296c-146">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="0296c-147">*全員* リンクを許可したいが、誤って認証されない共有が心配な場合は、他のオプションのいずれかを既定として検討してください。</span><span class="sxs-lookup"><span data-stu-id="0296c-147">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="0296c-148">このリンクの種類は、**全員** 共有を有効にしている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0296c-148">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="0296c-149">**組織内のユーザーのみ** - ほとんどのファイルとフォルダーの共有が組織内のユーザーと行われることが予想される場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0296c-149">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="0296c-150">**特定のユーザー** - ゲストと多くのファイルやフォルダーを共有することが予想される場合は、このオプションを検討してください。</span><span class="sxs-lookup"><span data-stu-id="0296c-150">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="0296c-151">この種類のリンクはゲストと連携し、ゲストに認証を要求します。</span><span class="sxs-lookup"><span data-stu-id="0296c-151">This type of link works with guests and requires them to authenticate.</span></span>
 
![SharePoint 組織レベルのファイルとフォルダーの共有設定のスクリーンショット](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="0296c-153">組織レベルの既定SharePointのOneDriveのリンク設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="0296c-153">To set the SharePoint and OneDrive organization-level default link settings</span></span>

1. <span data-ttu-id="0296c-154">SharePoint 管理センターの共有ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="0296c-154">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="0296c-155">**ファイルとフォルダーのリンク** で、使用する既定の共有リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="0296c-155">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="0296c-156">変更を加えた場合は、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0296c-156">If you made changes, click **Save**.</span></span>

<span data-ttu-id="0296c-157">共有リンクのアクセス許可を設定するには、[リンクの共有に既定で選択されているアクセス許可 **を選択する] で選択します。**</span><span class="sxs-lookup"><span data-stu-id="0296c-157">To set the permission for the sharing link, under **Choose the permission that's selected by default for sharing links.**</span></span>

1. <span data-ttu-id="0296c-158">認証 **されていないユーザー** がファイルとフォルダーを変更しない場合は、[表示] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0296c-158">Select **View** if you do not want unauthenticated users to make changes to the files and folders.</span></span>
2. <span data-ttu-id="0296c-159">認証 **されていないユーザー** がファイルとフォルダーに変更を加えるのを許可する場合は、[編集] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0296c-159">Select **Edit** if you want to allow unauthenticated users to make changes to the files and folders.</span></span>

<span data-ttu-id="0296c-160">上記の 2 つの事前入力オプションは、ゲスト/外部ユーザーだけでなく、内部ユーザーにも適用できます。</span><span class="sxs-lookup"><span data-stu-id="0296c-160">Note that the above two premission-options can be applied not only for guests/external users but also for internal users.</span></span> <span data-ttu-id="0296c-161">選択するアクセス許可オプションは、自己判断によって決まります。</span><span class="sxs-lookup"><span data-stu-id="0296c-161">The permission-option you choose is determined by self-discretion.</span></span>

<span data-ttu-id="0296c-162">誰とでも共有できるリンクのアクセス許可を設定するには</span><span class="sxs-lookup"><span data-stu-id="0296c-162">To set permissions for links that allow sharing with anyone</span></span>

1. <span data-ttu-id="0296c-163">[これらの **リンクでは、次のアクセス許可を付与できます。**</span><span class="sxs-lookup"><span data-stu-id="0296c-163">Under the **These links can give these permissions:** sub-pane,</span></span> 
    1. <span data-ttu-id="0296c-164">[ファイル **]** ドロップダウン リストから、</span><span class="sxs-lookup"><span data-stu-id="0296c-164">From the **Files** drop-down list,</span></span> 
        - <span data-ttu-id="0296c-165">認証 **されていないユーザーが** ファイルに変更を加えるのを許可する場合は、[表示と編集] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0296c-165">Select **View and edit** if you want to allow unauthenticated users to make changes to the files.</span></span>
        - <span data-ttu-id="0296c-166">認証 **されていないユーザー** がファイルを変更しない場合は、[表示] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0296c-166">Select **View** if you do not want unauthenticated users to make changes to the files.</span></span>
    2. <span data-ttu-id="0296c-167">[フォルダー **]** ドロップダウン リストから、</span><span class="sxs-lookup"><span data-stu-id="0296c-167">From the **Folders** drop-down list,</span></span>
        - <span data-ttu-id="0296c-168">認証 **されていないユーザーが** フォルダーに変更を加えるのを許可する場合は、[表示、編集、アップロード] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0296c-168">Select **View, edit, and upload** if you want to allow unauthenticated users to make changes to the folders.</span></span>
        - <span data-ttu-id="0296c-169">認証 **されていないユーザー** がフォルダーに変更を加えたくない場合は、[表示] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0296c-169">Select **View** if you do not want unauthenticated users to make changes to the folders.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="0296c-170">SharePoint のサイト レベル共有設定のスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="0296c-170">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="0296c-171">SharePoint サイト内のファイルとフォルダーを共有する場合は、そのサイトのサイト レベルの共有設定も確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0296c-171">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![SharePoint サイトの外部共有設定のスクリーンショット](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="0296c-173">サイトレベルの共有設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="0296c-173">To set site-level sharing settings</span></span>

1. <span data-ttu-id="0296c-174">SharePoint 管理センターの左側のナビゲーション ウィンドウで、[**サイト**] を展開して [**アクティブなサイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0296c-174">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="0296c-175">ゲストとファイルやフォルダーを共有するサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="0296c-175">Select the site on which you want to share files and folders with guests.</span></span>
3. <span data-ttu-id="0296c-176">行 (選択したサイトが存在する) を右にスクロールし、[外部共有] 列の任意の **場所をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="0296c-176">Scroll right across the row (in which the selected site is present) and click anywhere in the **External sharing** column.</span></span>
4. <span data-ttu-id="0296c-177">ポップアップするページで、[ポリシー] タブ **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="0296c-177">From the page that pops up, click **Policies** tab.</span></span>
5. <span data-ttu-id="0296c-178">[外部共有 **] ウィンドウで、[** 編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="0296c-178">Under the **External sharing** pane, click **Edit**.</span></span>
6. <span data-ttu-id="0296c-179">共有が **[全員]** または **[新規および既存のゲスト]** に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0296c-179">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
7. <span data-ttu-id="0296c-180">変更を加えた場合は、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0296c-180">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="0296c-181">ユーザーを招待する</span><span class="sxs-lookup"><span data-stu-id="0296c-181">Invite users</span></span>

<span data-ttu-id="0296c-182">ゲスト共有の設定が構成されています。これで、ユーザーは組織外のユーザーとファイルやフォルダーを共有できます。</span><span class="sxs-lookup"><span data-stu-id="0296c-182">Guest-sharing settings are now configured; so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="0296c-183">詳細[については、「OneDriveファイルとフォルダーの共有](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07)」および[「SharePointフォルダーの共有」](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0296c-183">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="0296c-184">関連項目</span><span class="sxs-lookup"><span data-stu-id="0296c-184">See also</span></span>

[<span data-ttu-id="0296c-185">認証されていないユーザーとファイルおよびフォルダーを共有するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="0296c-185">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="0296c-186">ゲストと共有するときにファイルの偶発的な公開を制限する</span><span class="sxs-lookup"><span data-stu-id="0296c-186">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="0296c-187">SharePoint および OneDrive の Azure AD B2B との統合</span><span class="sxs-lookup"><span data-stu-id="0296c-187">SharePoint and OneDrive integration with Azure AD B2B</span></span>](/sharepoint/sharepoint-azureb2b-integration-preview)