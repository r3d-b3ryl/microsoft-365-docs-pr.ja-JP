---
title: ゲストと共同でドキュメントの作業をする
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
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: この記事では、SharePoint および OneDrive のドキュメントでゲストを使用して共同作業を行う方法について説明します。
ms.openlocfilehash: 022811be642a79c07c632cefcc67a27f19e3af4f
ms.sourcegitcommit: 39af527404cb06e05c5aa4550dbec39aec133016
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2020
ms.locfileid: "48422607"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="2f15a-103">ゲストと共同でドキュメントの作業をする</span><span class="sxs-lookup"><span data-stu-id="2f15a-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="2f15a-104">SharePoint または OneDrive のドキュメントで組織外のユーザーと共同作業を行う必要がある場合は、ドキュメントへの共有リンクを送信することができます。</span><span class="sxs-lookup"><span data-stu-id="2f15a-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing-link to the document.</span></span> <span data-ttu-id="2f15a-105">この記事では、組織のニーズに合わせて SharePoint と OneDrive の共有リンクを設定するために必要な、Microsoft 365 の構成手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="2f15a-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing-links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="2f15a-106">ビデオ デモンストレーション</span><span class="sxs-lookup"><span data-stu-id="2f15a-106">Video demonstration</span></span>

<span data-ttu-id="2f15a-107">このビデオでは、このドキュメントで説明されている構成手順を示します。</span><span class="sxs-lookup"><span data-stu-id="2f15a-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="2f15a-108">Azure の組織上の関係の設定</span><span class="sxs-lookup"><span data-stu-id="2f15a-108">Azure organizational relationships settings</span></span>

<span data-ttu-id="2f15a-109">Microsoft 365 での共有は、 [Azure Active Directory の組織上の関係の設定](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)によって最上位レベルで管理されます。</span><span class="sxs-lookup"><span data-stu-id="2f15a-109">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="2f15a-110">Azure AD でゲスト共有が無効または制限されている場合、この設定は、Microsoft 365 で構成した共有設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="2f15a-110">If guest-sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="2f15a-111">組織上の関係の設定を確認して、ゲストとの共有がブロックされないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="2f15a-111">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Azure Active Directory における組織の関係の設定ページのスクリーンショット](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="2f15a-113">組織上の関係の設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="2f15a-113">To set organizational relationship settings</span></span>

<span data-ttu-id="2f15a-114">外部グループ作業設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="2f15a-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="2f15a-115">Azure Active Directory にログイン [https://aad.portal.azure.com](https://aad.portal.azure.com) します。</span><span class="sxs-lookup"><span data-stu-id="2f15a-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="2f15a-116">左側のナビゲーションウィンドウで、[ **Azure Active Directory**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f15a-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="2f15a-117">[ **外部 id**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f15a-117">Click **External identities**.</span></span>
4. <span data-ttu-id="2f15a-118">[ **作業の開始** ] 画面の左側のナビゲーションウィンドウで、[ **外部グループ作業の設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f15a-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="2f15a-119">**管理者とゲスト招待元役割のユーザーが招待できる**ことと、**メンバーが招待**できることを確認します。どちらも **[はい]** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="2f15a-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="2f15a-120">変更を加えた場合は、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f15a-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="2f15a-121">[ **共同作業の制限** ] セクションの設定に注意してください。</span><span class="sxs-lookup"><span data-stu-id="2f15a-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="2f15a-122">共同作業を行うゲストのドメインがブロックされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="2f15a-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="2f15a-123">複数の組織のゲストを使用している場合は、ディレクトリデータへのアクセスを制限することをお客様に許可します。</span><span class="sxs-lookup"><span data-stu-id="2f15a-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="2f15a-124">これにより、他のユーザーがディレクトリ内のゲストであることを確認できなくなります。</span><span class="sxs-lookup"><span data-stu-id="2f15a-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="2f15a-125">これを行うには、[ **ゲストユーザーのアクセス制限**] で、[ゲストユーザー **がアクセスを制限しているのは、ディレクトリオブジェクトのプロパティとメンバーシップ] 設定** または **guest ユーザーアクセスが、自分のディレクトリオブジェクトのプロパティとメンバーシップに制限され**ています。</span><span class="sxs-lookup"><span data-stu-id="2f15a-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="2f15a-126">SharePoint 組織レベルでの共有設定</span><span class="sxs-lookup"><span data-stu-id="2f15a-126">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="2f15a-127">組織外のユーザーが SharePoint または OneDrive のドキュメントにアクセスできるようにするには、SharePoint および OneDrive の組織レベルでの共有設定で、組織外のユーザーとの共有が許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f15a-127">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="2f15a-128">SharePoint の組織レベルの設定により、個々の SharePoint サイトで使用できる設定が決定されます。</span><span class="sxs-lookup"><span data-stu-id="2f15a-128">The organization-level settings for SharePoint determine the settings that will be available for individual SharePoint sites.</span></span> <span data-ttu-id="2f15a-129">サイトの設定は、組織レベルの設定よりも制限することはできません。</span><span class="sxs-lookup"><span data-stu-id="2f15a-129">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="2f15a-130">OneDrive の組織レベルの設定により、ユーザーの OneDrive ライブラリで利用できる共有のレベルが決定されます。</span><span class="sxs-lookup"><span data-stu-id="2f15a-130">The organization-level setting for OneDrive determines the level of sharing that will be available in users' OneDrive libraries.</span></span>

<span data-ttu-id="2f15a-131">SharePoint と OneDrive の場合は、認証されていないファイルとフォルダーの共有を許可する場合は、[ **すべて**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2f15a-131">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="2f15a-132">組織外のユーザーが認証を必要とするようにするには、[ **新規および既存のゲスト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2f15a-132">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="2f15a-133">[*全員*] リンクは最も簡単に共有する方法です。組織外のユーザーは、認証なしでリンクを開くことができ、他のユーザーに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="2f15a-133">*Anyone* links is the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="2f15a-134">SharePoint の場合は、組織内のすべてのサイトで必要とされる最も寛容な設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="2f15a-134">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 組織レベルの共有設定のスクリーンショット](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="2f15a-136">SharePoint 組織レベルの共有設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="2f15a-136">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="2f15a-137">Microsoft 365 管理センターの左側のナビゲーションウィンドウで、[ **管理センター**] の下の [ **SharePoint**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f15a-137">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="2f15a-138">SharePoint 管理センターの左側のナビゲーションウィンドウで、[ **ポリシー**] の下にある [ **共有**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f15a-138">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="2f15a-139">SharePoint または OneDrive の外部共有が [すべての **ユーザー** ] または **[既存のゲスト**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2f15a-139">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="2f15a-140">(OneDrive の設定は、SharePoint の設定よりも制限がないことに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="2f15a-140">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="2f15a-141">変更を加えた場合は、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f15a-141">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="2f15a-142">SharePoint 組織レベルの既定のリンク設定</span><span class="sxs-lookup"><span data-stu-id="2f15a-142">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="2f15a-143">既定のファイルおよびフォルダーのリンク設定は、ファイルまたはフォルダーを共有するときに既定でユーザーに表示されるリンクオプションを決定します。</span><span class="sxs-lookup"><span data-stu-id="2f15a-143">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="2f15a-144">必要に応じて、共有する前に、リンクの種類を他のオプションのいずれかに変更できます。</span><span class="sxs-lookup"><span data-stu-id="2f15a-144">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="2f15a-145">この設定は、組織内の SharePoint サイトや OneDrive に影響を与えることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2f15a-145">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="2f15a-146">ユーザーがファイルやフォルダーを共有するときに既定で選択される、次のいずれかの種類のリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="2f15a-146">Choose a link from any of the following types which is then selected by default when users share files and folders:</span></span>

- <span data-ttu-id="2f15a-147">**リンクを持つすべてのユーザー** -認証されていないファイルとフォルダーの共有が頻繁に行われるようにする場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="2f15a-147">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="2f15a-148">*すべて*のリンクを許可し、偶発的な認証されていない共有について懸念している場合は、他のオプションのいずれかを既定値として検討します。</span><span class="sxs-lookup"><span data-stu-id="2f15a-148">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="2f15a-149">このリンクの種類は、 **すべて** の共有を有効にした場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2f15a-149">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="2f15a-150">[**組織内のユーザーのみ**]-ほとんどのファイルとフォルダーの共有が組織内のユーザーと想定される場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="2f15a-150">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="2f15a-151">**特定のユーザー** -多数のファイルとフォルダーをゲストで共有することが予想される場合は、このオプションを検討してください。</span><span class="sxs-lookup"><span data-stu-id="2f15a-151">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="2f15a-152">この種類のリンクはゲストと連動しており、認証を必要とします。</span><span class="sxs-lookup"><span data-stu-id="2f15a-152">This type of link works with guests and requires them to authenticate.</span></span>
 
![SharePoint における組織レベルのファイルとフォルダー設定のスクリーンショット](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="2f15a-154">SharePoint と OneDrive の組織レベルの既定のリンク設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="2f15a-154">To set the SharePoint and OneDrive organization-level default link settings</span></span>

1. <span data-ttu-id="2f15a-155">SharePoint 管理センターの [共有] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="2f15a-155">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="2f15a-156">[ **ファイルとフォルダーのリンク**] で、使用する既定の共有リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="2f15a-156">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="2f15a-157">変更を加えた場合は、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f15a-157">If you made changes, click **Save**.</span></span>

<span data-ttu-id="2f15a-158">共有リンクのアクセス許可を設定するには、[ **共有リンク] で既定で選択されているアクセス許可を選択します。**</span><span class="sxs-lookup"><span data-stu-id="2f15a-158">To set the permission for the sharing link, under **Choose the permission that's selected by default for sharing links.**</span></span>

1. <span data-ttu-id="2f15a-159">認証されていないユーザーがファイルやフォルダーを変更できないようにする場合は、[ **表示** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2f15a-159">Select **View** if you do not want unauthenticated users to make changes to the files and folders.</span></span>
2. <span data-ttu-id="2f15a-160">認証されていないユーザーがファイルやフォルダーを変更できるようにする場合は、[ **編集** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2f15a-160">Select **Edit** if you want to allow unauthenticated users to make changes to the files and folders.</span></span>

<span data-ttu-id="2f15a-161">上記の2つの事前ミッションオプションは、ゲスト/外部ユーザーに対してだけでなく、内部ユーザーに対しても適用できます。</span><span class="sxs-lookup"><span data-stu-id="2f15a-161">Note that the above two premission-options can be applied not only for guests/external users but also for internal users.</span></span> <span data-ttu-id="2f15a-162">選択する権限オプションは、自己決定によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="2f15a-162">The permission-option you choose is determined by self-discretion.</span></span>

<span data-ttu-id="2f15a-163">他のユーザーとの共有を許可するリンクにアクセス許可を設定するには</span><span class="sxs-lookup"><span data-stu-id="2f15a-163">To set permissions for links that allow sharing with anyone</span></span>

1. <span data-ttu-id="2f15a-164">これらのリンクでは、次の **アクセス許可を付与できます:** サブウィンドウ</span><span class="sxs-lookup"><span data-stu-id="2f15a-164">Under the **These links can give these permissions:** sub-pane,</span></span> 
    1. <span data-ttu-id="2f15a-165">[ **ファイル** ] ドロップダウンリストから、</span><span class="sxs-lookup"><span data-stu-id="2f15a-165">From the **Files** drop-down list,</span></span> 
        1. <span data-ttu-id="2f15a-166">認証されていないユーザーがファイルに変更を加えることを許可する場合は **、[表示と編集** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2f15a-166">Select **View and edit** if you want to allow unauthenticated users to make changes to the files.</span></span>
        2. <span data-ttu-id="2f15a-167">認証されていないユーザーがファイルを変更できないようにする場合は、[ **表示** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2f15a-167">Select **View** if you do not want unauthenticated users to make changes to the files.</span></span>
    2. <span data-ttu-id="2f15a-168">[ **フォルダー** ] ボックスの一覧から、</span><span class="sxs-lookup"><span data-stu-id="2f15a-168">From the **Folders** drop-down list,</span></span>
        1. <span data-ttu-id="2f15a-169">認証されていないユーザーがフォルダーの変更を行えるようにする場合は、[ **表示、編集、およびアップロード** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2f15a-169">Select **View, edit, and upload** if you want to allow unauthenticated users to make changes to the folders.</span></span>
        2. <span data-ttu-id="2f15a-170">認証されていないユーザーがフォルダーを変更できないようにする場合は、[ **表示** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2f15a-170">Select **View** if you do not want unauthenticated users to make changes to the folders.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="2f15a-171">SharePoint サイトレベルの共有設定</span><span class="sxs-lookup"><span data-stu-id="2f15a-171">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="2f15a-172">SharePoint サイト内のファイルとフォルダーを共有している場合は、そのサイトのサイトレベルの共有設定も確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f15a-172">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![SharePoint サイトの外部共有設定のスクリーンショット](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="2f15a-174">サイトレベルの共有設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="2f15a-174">To set site-level sharing settings</span></span>

1. <span data-ttu-id="2f15a-175">SharePoint 管理センターの左側のナビゲーションウィンドウで、[ **サイト** ] を展開し、[ **アクティブなサイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f15a-175">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="2f15a-176">ゲストでファイルとフォルダーを共有するサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="2f15a-176">Select the site on which you want to share files and folders with guests.</span></span>
3. <span data-ttu-id="2f15a-177">選択したサイトが表示されている行で右にスクロールし、[ **外部共有** ] 列の任意の場所をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f15a-177">Scroll right across the row (in which the selected site is present) and click anywhere in the **External sharing** column.</span></span>
4. <span data-ttu-id="2f15a-178">ポップアップ表示されたページで、[ **ポリシー** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f15a-178">From the page that pops up, click **Policies** tab.</span></span>
5. <span data-ttu-id="2f15a-179">[ **外部共有** ] ウィンドウで、[ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f15a-179">Under the **External sharing** pane, click **Edit**.</span></span>
6. <span data-ttu-id="2f15a-180">共有が [ **すべてのユーザー** ] または **[既存のゲスト**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2f15a-180">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
7. <span data-ttu-id="2f15a-181">変更を加えた場合は、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f15a-181">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="2f15a-182">ユーザーを招待する</span><span class="sxs-lookup"><span data-stu-id="2f15a-182">Invite users</span></span>

<span data-ttu-id="2f15a-183">ゲスト共有の設定が構成されるようになりました。これにより、ユーザーは、組織外のユーザーとファイルやフォルダーを共有できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2f15a-183">Guest-sharing settings are now configured; so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="2f15a-184">詳細については、「 [OneDrive ファイルとフォルダーを共有](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) する」および「 [SharePoint ファイルまたはフォルダーを共有](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f15a-184">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f15a-185">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f15a-185">See also</span></span>

[<span data-ttu-id="2f15a-186">認証されていないユーザーとファイルおよびフォルダーを共有するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="2f15a-186">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="2f15a-187">ゲストと共有するときにファイルの偶発的な公開を制限する</span><span class="sxs-lookup"><span data-stu-id="2f15a-187">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="2f15a-188">Azure AD B2B を使用した SharePoint と OneDrive の統合</span><span class="sxs-lookup"><span data-stu-id="2f15a-188">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
