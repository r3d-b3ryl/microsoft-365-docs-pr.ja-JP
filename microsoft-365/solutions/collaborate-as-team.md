---
title: チームでゲストと共同で作業する
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
description: Teams のゲストとのタスク、会話、ドキュメントの共同作業用にチームをセットアップするために必要な Microsoft 365 構成手順について説明します。
ms.openlocfilehash: 34b7d5d47d7fb0c9196beda70184fa6510b6cc33
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780546"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="1f6de-103">チームでゲストと共同で作業する</span><span class="sxs-lookup"><span data-stu-id="1f6de-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="1f6de-104">ドキュメント、タスク、会話を通じてゲストと共同作業する必要がある場合は、Microsoft Teams を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1f6de-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="1f6de-105">Teams は、Office と SharePoint で利用可能なすべてのコラボレーション機能を、常設チャットと、統一されたユーザー エクスペリエンスでカスタマイズ可能で拡張可能なコラボレーション ツールのセットで提供します。</span><span class="sxs-lookup"><span data-stu-id="1f6de-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="1f6de-106">この記事では、ゲストと共同作業するためのチームをセットアップするために必要な Microsoft 365 の構成手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="1f6de-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="1f6de-107">ビデオ デモンストレーション</span><span class="sxs-lookup"><span data-stu-id="1f6de-107">Video demonstration</span></span>

<span data-ttu-id="1f6de-108">このビデオでは、このドキュメントで説明されている構成手順を示します。</span><span class="sxs-lookup"><span data-stu-id="1f6de-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="1f6de-109">Azure 外部コラボレーションの設定</span><span class="sxs-lookup"><span data-stu-id="1f6de-109">Azure External collaboration settings</span></span>

<span data-ttu-id="1f6de-110">Microsoft 365 での共有は、Azure Active Directory の B2B 外部コラボレーション設定によって最高レベル [で管理されます](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)。</span><span class="sxs-lookup"><span data-stu-id="1f6de-110">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="1f6de-111">Azure AD でゲスト共有が無効または制限されている場合、この設定は Microsoft 365 で構成した共有設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="1f6de-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="1f6de-112">B2B 外部コラボレーション設定を確認して、ゲストとの共有がブロックされていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="1f6de-112">Check the B2B external collaboration settings settings to ensure that sharing with guests is not blocked.</span></span>

![Azure Active Directory における組織の関係の設定ページのスクリーンショット](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="1f6de-114">外部コラボレーション設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="1f6de-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="1f6de-115">Azure Active Directory にログインします [https://aad.portal.azure.com](https://aad.portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="1f6de-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="1f6de-116">左側のナビゲーション ウィンドウで **、Azure Active Directory をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1f6de-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="1f6de-117">[外部 **ID] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1f6de-117">Click **External identities**.</span></span>
4. <span data-ttu-id="1f6de-118">[作業の **開始] 画面** の左側のナビゲーション ウィンドウで、[外部コラボレーションの設定 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1f6de-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="1f6de-119">管理者と **ゲスト招待者の役割のユーザーが** 招待可能であり、 **メンバー** が招待可能な両方が [はい] **に設定されています**。</span><span class="sxs-lookup"><span data-stu-id="1f6de-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="1f6de-120">変更を加えた場合は、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f6de-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="1f6de-121">[コラボレーションの制限] セクション **の設定に注意** してください。</span><span class="sxs-lookup"><span data-stu-id="1f6de-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="1f6de-122">共同作業を行うゲストのドメインがブロックされていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="1f6de-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="1f6de-123">複数の組織のゲストと連携する場合は、ディレクトリ データにアクセスする機能を制限できます。</span><span class="sxs-lookup"><span data-stu-id="1f6de-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="1f6de-124">これにより、他のユーザーがディレクトリのゲストであるのを見るのを防ぐのに使用できます。</span><span class="sxs-lookup"><span data-stu-id="1f6de-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="1f6de-125">これを行うには、[ゲストユーザーのアクセス制限]で、[ゲスト ユーザーがディレクトリ オブジェクトの設定のプロパティとメンバーシップに制限されたアクセス権を持っている] を選択するか、[ゲスト ユーザー アクセス] を自分のディレクトリ オブジェクトのプロパティとメンバーシップに制限 **します。**</span><span class="sxs-lookup"><span data-stu-id="1f6de-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="1f6de-126">Teams のゲスト アクセス設定</span><span class="sxs-lookup"><span data-stu-id="1f6de-126">Teams guest access settings</span></span>

<span data-ttu-id="1f6de-127">Teams には、ゲスト アクセス用のマスター オン/オフ スイッチと、ゲストがチームで実行できる操作を制御できるさまざまな設定があります。</span><span class="sxs-lookup"><span data-stu-id="1f6de-127">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="1f6de-128">ゲスト アクセスが Teams **で機能するには、マスター** スイッチ (Teams でのゲスト アクセスを **許可** する) がオンである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f6de-128">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="1f6de-129">Teams でゲスト アクセスが有効になっているか確認し、ビジネス ニーズに基づいてゲスト設定を調整します。</span><span class="sxs-lookup"><span data-stu-id="1f6de-129">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="1f6de-130">これらの設定は、すべてのチームに影響を与えるという念頭に置きます。</span><span class="sxs-lookup"><span data-stu-id="1f6de-130">Keep in mind that these settings affect all teams.</span></span>

![Teams ゲスト アクセスのトグルのスクリーンショット](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="1f6de-132">Teams ゲスト アクセスの設定を行うには</span><span class="sxs-lookup"><span data-stu-id="1f6de-132">To set Teams guest access settings</span></span>

1. <span data-ttu-id="1f6de-133">[https://admin.microsoft.com](https://admin.microsoft.com) で、Microsoft 365 管理センターにログインします。</span><span class="sxs-lookup"><span data-stu-id="1f6de-133">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="1f6de-134">左側のナビゲーション ウィンドウで、[すべて表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1f6de-134">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="1f6de-135">[**管理センター**] で、[**Teams**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f6de-135">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="1f6de-136">Teams 管理センターの左側のナビゲーション ウィンドウで、[組織全体の設定] を展開し、[ゲスト アクセス]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1f6de-136">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="1f6de-137">[**Teams でのゲスト アクセスを許可する**] が [**オン**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f6de-137">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="1f6de-138">追加のゲスト設定に必要な変更を加えて、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f6de-138">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

<span data-ttu-id="1f6de-139">Teams のゲスト アクセスを有効にすると、必要に応じて、個別のチームおよび関連する SharePoint サイトへのゲスト アクセスを、区別ラベルを使用して制御できます。</span><span class="sxs-lookup"><span data-stu-id="1f6de-139">Once Teams guest access is turned on, you can optionally control guest access to individual teams and their associated SharePoint sites using sensitivity labels.</span></span> <span data-ttu-id="1f6de-140">詳細については、「[機密ラベルを使用して、Microsoft Teams、Office 365 グループ、SharePoint サイトのコンテンツを保護する](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)」 をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1f6de-140">For more information, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

> [!NOTE]
> <span data-ttu-id="1f6de-141">Teams のゲスト設定を有効にした後にアクティブになるには、最大で 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1f6de-141">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="1f6de-142">Microsoft 365 グループのゲスト設定</span><span class="sxs-lookup"><span data-stu-id="1f6de-142">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="1f6de-143">Teams は、チーム メンバーシップに Microsoft 365 グループを使用します。</span><span class="sxs-lookup"><span data-stu-id="1f6de-143">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="1f6de-144">Teams のゲスト アクセスを機能するには、Microsoft 365 グループのゲスト設定を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f6de-144">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Microsoft 365 管理センターにおける Microsoft 365 グループのゲスト設定のスクリーンショット](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="1f6de-146">Microsoft 365 グループのゲスト設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="1f6de-146">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="1f6de-147">Microsoft 365 管理センターの左側のナビゲーション ウィンドウで、[設定] を **展開します**。</span><span class="sxs-lookup"><span data-stu-id="1f6de-147">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="1f6de-148">[ **組織の設定] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1f6de-148">Click **Org settings**.</span></span>
3. <span data-ttu-id="1f6de-149">一覧で **、[Microsoft 365 グループ] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1f6de-149">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="1f6de-150">[グループ所有者が組織外のユーザーをゲストとして **Microsoft 365 グループ** に追加する] チェック ボックスと [ゲスト グループ のメンバーがグループ コンテンツにアクセスする] の両方のチェック ボックスがオンになっています。</span><span class="sxs-lookup"><span data-stu-id="1f6de-150">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="1f6de-151">変更を加えた場合は、[変更の保存] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1f6de-151">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="1f6de-152">SharePoint 組織レベルの共有設定</span><span class="sxs-lookup"><span data-stu-id="1f6de-152">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="1f6de-153">ファイル、フォルダー、リストなどの Teams コンテンツはすべて SharePoint に保存されます。</span><span class="sxs-lookup"><span data-stu-id="1f6de-153">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="1f6de-154">ゲストが Teams でこれらのアイテムにアクセスするには、SharePoint 組織レベルの共有設定でゲストとの共有を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f6de-154">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="1f6de-155">組織レベルの設定では、チームに関連付けられているサイトを含む、個々のサイトで使用できる設定を決定します。</span><span class="sxs-lookup"><span data-stu-id="1f6de-155">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="1f6de-156">サイトの設定を組織レベルの設定よりも制限することはできません。</span><span class="sxs-lookup"><span data-stu-id="1f6de-156">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="1f6de-157">認証されていないユーザーとのファイルとフォルダーの共有を許可する場合は、[すべてのユーザー] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="1f6de-157">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="1f6de-158">すべてのゲストを認証する必要がある場合は、[新規および既存のゲスト] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1f6de-158">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="1f6de-159">組織内の任意のサイトで必要になる最も制限の多い設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f6de-159">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 組織レベルの共有設定のスクリーンショット](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="1f6de-161">SharePoint 組織レベルの共有設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="1f6de-161">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="1f6de-162">Microsoft 365 管理センターの左側のナビゲーション ウィンドウで、[管理センター] の下の **[SharePoint] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1f6de-162">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="1f6de-163">SharePoint 管理センターの左側のナビゲーション ウィンドウで、[ポリシー  ] を展開し、[共有] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="1f6de-163">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="1f6de-164">SharePoint の外部共有が [すべてのユーザー] または **[新規]** および [既存の **ゲスト] に設定されている必要があります**。</span><span class="sxs-lookup"><span data-stu-id="1f6de-164">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="1f6de-165">変更を加えた場合は、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f6de-165">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="1f6de-166">SharePoint 組織レベルの既定のリンク設定</span><span class="sxs-lookup"><span data-stu-id="1f6de-166">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="1f6de-167">既定のファイルとフォルダーのリンク設定によって、ユーザーがファイルまたはフォルダーを共有するときに既定で表示されるリンク オプションが決きます。</span><span class="sxs-lookup"><span data-stu-id="1f6de-167">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="1f6de-168">ユーザーは、必要に応じて、共有する前にリンクの種類を他のオプションの 1 つに変更できます。</span><span class="sxs-lookup"><span data-stu-id="1f6de-168">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="1f6de-169">この設定は、組織内のすべてのチームと SharePoint サイトに影響を与える点に気を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f6de-169">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="1f6de-170">ユーザーがファイルとフォルダーを共有するときに既定で選択される、次のいずれかのリンクの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="1f6de-170">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="1f6de-171">**リンクを持つすべてのユーザー** - ファイルとフォルダーの認証されていない共有を多く行う場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="1f6de-171">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="1f6de-172">[すべてのユーザー]リンクを許可するが、認証されていない誤った共有を懸念している場合は、他のオプションのいずれかを既定として検討します。</span><span class="sxs-lookup"><span data-stu-id="1f6de-172">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="1f6de-173">このリンクの種類は、[すべてのユーザー] 共有を有効にしている場合 **にのみ使用** できます。</span><span class="sxs-lookup"><span data-stu-id="1f6de-173">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="1f6de-174">**組織内のユーザーのみ** - ほとんどのファイルとフォルダーの共有が組織内のユーザーと行う必要がある場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="1f6de-174">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="1f6de-175">**特定のユーザー** - ゲストと多くのファイルとフォルダーの共有を行う場合は、このオプションを検討してください。</span><span class="sxs-lookup"><span data-stu-id="1f6de-175">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="1f6de-176">この種類のリンクはゲストと一緒に機能し、認証を必要とします。</span><span class="sxs-lookup"><span data-stu-id="1f6de-176">This type of link works with guests and requires them to authenticate.</span></span>
 
![SharePoint における組織レベルのファイルとフォルダー設定のスクリーンショット](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="1f6de-178">SharePoint 組織レベルの既定のリンク設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="1f6de-178">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="1f6de-179">SharePoint 管理センターの [共有] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="1f6de-179">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="1f6de-180">[ **ファイルとフォルダーのリンク] で**、使用する既定の共有リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="1f6de-180">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="1f6de-181">変更を加えた場合は、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f6de-181">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="1f6de-182">チームを作成する</span><span class="sxs-lookup"><span data-stu-id="1f6de-182">Create a team</span></span>

<span data-ttu-id="1f6de-183">次の手順では、ゲストとの共同作業に使用する予定のチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f6de-183">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="1f6de-184">チームを作成するには</span><span class="sxs-lookup"><span data-stu-id="1f6de-184">To create a team</span></span>
1. <span data-ttu-id="1f6de-185">Teams の **[Teams]** タブで、左側のウィンドウの下部にある [参加] をクリックするか、チームを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f6de-185">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="1f6de-186">[チーム **の作成] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1f6de-186">Click **Create a team**.</span></span>
3. <span data-ttu-id="1f6de-187">[チーム **を最初から作成する] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1f6de-187">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="1f6de-188">[プライベート **] または [** パブリック] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="1f6de-188">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="1f6de-189">チームの名前と説明を入力し、[作成] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="1f6de-189">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="1f6de-190">[ **スキップ] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1f6de-190">Click **Skip**.</span></span>

<span data-ttu-id="1f6de-191">後でユーザーを招待します。</span><span class="sxs-lookup"><span data-stu-id="1f6de-191">We'll invite users later.</span></span> <span data-ttu-id="1f6de-192">次に、チームに関連付けられている SharePoint サイトのサイト レベルの共有設定を確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="1f6de-192">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="1f6de-193">SharePoint サイト レベルの共有設定</span><span class="sxs-lookup"><span data-stu-id="1f6de-193">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="1f6de-194">サイト レベルの共有設定を確認して、このチームに必要なアクセスの種類を許可します。</span><span class="sxs-lookup"><span data-stu-id="1f6de-194">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="1f6de-195">たとえば、組織レベルの設定を **[** すべてのユーザー] に設定し、すべてのゲストをこのチームで認証する場合は、サイト レベルの共有設定が [新規] および [既存のゲスト] に設定されている必要 **があります。**</span><span class="sxs-lookup"><span data-stu-id="1f6de-195">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![SharePoint サイトの外部共有設定のスクリーンショット](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="1f6de-197">サイト レベルの共有設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="1f6de-197">To set site-level sharing settings</span></span>
1. <span data-ttu-id="1f6de-198">SharePoint 管理センターの左側のナビゲーション ウィンドウで、[サイト] を展開し、[アクティブ **なサイト]** **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1f6de-198">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="1f6de-199">作成したチームのサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="1f6de-199">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="1f6de-200">[...] をクリックします。を選択 **し、[共有] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1f6de-200">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="1f6de-201">共有が [すべてのユーザー] または [ **新規** ] および [既存の **ゲスト] に設定されている必要があります**。</span><span class="sxs-lookup"><span data-stu-id="1f6de-201">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="1f6de-202">変更を加えた場合は、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f6de-202">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="1f6de-203">ユーザーを招待する</span><span class="sxs-lookup"><span data-stu-id="1f6de-203">Invite users</span></span>

<span data-ttu-id="1f6de-204">ゲスト共有の設定が構成されたので、チームへの内部ユーザーとゲストの追加を開始できます。</span><span class="sxs-lookup"><span data-stu-id="1f6de-204">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="1f6de-205">内部ユーザーをチームに招待するには</span><span class="sxs-lookup"><span data-stu-id="1f6de-205">To invite internal users to a team</span></span>
1. <span data-ttu-id="1f6de-206">チームで、[その他のオプション ( ] を **クリックし** 、[ **\*\*\*** メンバーの追加] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1f6de-206">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="1f6de-207">招待するユーザーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="1f6de-207">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="1f6de-208">**[追加]** をクリックして、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f6de-208">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="1f6de-209">ゲストをチームに招待する</span><span class="sxs-lookup"><span data-stu-id="1f6de-209">To invite guests to a team</span></span>
1. <span data-ttu-id="1f6de-210">チームで、[その他のオプション ( ] を **クリック** し、[ **\*\*\*** メンバーの追加] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1f6de-210">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="1f6de-211">招待するゲストのメール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="1f6de-211">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="1f6de-212">[ゲスト **情報の編集] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1f6de-212">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="1f6de-213">ゲストのフル ネームを入力し、チェック マークをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f6de-213">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="1f6de-214">**[追加]** をクリックして、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f6de-214">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f6de-215">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f6de-215">See also</span></span>

[<span data-ttu-id="1f6de-216">認証されていないユーザーとファイルおよびフォルダーを共有するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="1f6de-216">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="1f6de-217">ゲストと共有するときにファイルの偶発的な公開を制限する</span><span class="sxs-lookup"><span data-stu-id="1f6de-217">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="1f6de-218">セキュリティで保護されたゲスト共有環境を作成する</span><span class="sxs-lookup"><span data-stu-id="1f6de-218">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="1f6de-219">管理されたゲストで B2B エクストラネットを作成する</span><span class="sxs-lookup"><span data-stu-id="1f6de-219">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="1f6de-220">SharePoint と OneDrive と Azure AD B2B の統合</span><span class="sxs-lookup"><span data-stu-id="1f6de-220">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)

[<span data-ttu-id="1f6de-221">SharePoint または OneDrive から共有すると、共有オプションは灰色表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f6de-221">Sharing options are greyed out when sharing from SharePoint or OneDrive</span></span>](https://docs.microsoft.com/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)
