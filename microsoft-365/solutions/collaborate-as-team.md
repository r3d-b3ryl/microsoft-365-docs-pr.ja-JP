---
title: チームでゲストと共同作業する
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
localization_priority: Priority
f1.keywords: NOCSH
recommendations: false
description: Teams のゲストとのタスク、会話、ドキュメントの共同作業を行うためチームをセットアップするのに必要な Microsoft 365 の構成手順について説明します。
ms.openlocfilehash: c17732705c1d88ff70e56f5d26d9e268e3ff7c19
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539265"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="5aaf7-103">チームでゲストと共同作業する</span><span class="sxs-lookup"><span data-stu-id="5aaf7-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="5aaf7-104">ドキュメント、タスク、会話全体でゲストと共同作業する必要がある場合は、Microsoft Teams の使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="5aaf7-105">Teams は、Office と SharePoint で利用可能なすべての共同作業の機能を、常設チャットと、カスタマイズ可能で拡張可能な共同作業のツールのセットを使用して、統合されたユーザー操作環境で提供します。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="5aaf7-106">この記事では、ゲストとの共同作業のためチームをセットアップするのに必要な Microsoft 365 の構成手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span> <span data-ttu-id="5aaf7-107">ゲスト アクセスを構成したら、「[Teams でゲストをチームに追加する](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f)」の手順で、ゲストをチームに招待できます。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-107">Once you have configured guest access, you can invite guests to teams by following the steps in [Add guests to a team in Teams](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="5aaf7-108">ビデオ デモンストレーション</span><span class="sxs-lookup"><span data-stu-id="5aaf7-108">Video demonstration</span></span>

<span data-ttu-id="5aaf7-109">このビデオは、このドキュメントで説明されている構成手順を示しています。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-109">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="5aaf7-110">Azure 外部コラボレーションの設定</span><span class="sxs-lookup"><span data-stu-id="5aaf7-110">Azure External collaboration settings</span></span>

<span data-ttu-id="5aaf7-111">Microsoft 365 での共有は、[Azure Active Directory における B2B 外部コラボレーションの設定](/azure/active-directory/external-identities/delegate-invitations) によって最高レベルで管理されます。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-111">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="5aaf7-112">Azure AD でゲストの共有が無効になっているか、制限されている場合、この設定により、Microsoft 365 で構成した共有設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-112">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="5aaf7-113">B2B 外部コラボレーションの設定をチェックして、ゲストとの共有がブロックされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-113">Check the B2B external collaboration settings settings to ensure that sharing with guests is not blocked.</span></span>

![Azure Active Directory における組織関係の設定ページのスクリーンショット](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="5aaf7-115">外部コラボレーションを設定するには</span><span class="sxs-lookup"><span data-stu-id="5aaf7-115">To set external collaboration settings</span></span>

1. <span data-ttu-id="5aaf7-116">[https://aad.portal.azure.com](https://aad.portal.azure.com) で Azure Active Directory にログインします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-116">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="5aaf7-117">左側のナビゲーション ウィンドウで **[Azure Active Directory]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-117">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="5aaf7-118">**[外部 ID]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-118">Click **External identities**.</span></span>
4. <span data-ttu-id="5aaf7-119">**[開始]** 画面で、左側のナビゲーション ウィンドウで **[外部コラボレーション設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-119">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="5aaf7-120">**[管理者とゲスト招待者の役割のユーザーが招待できる]** と **[メンバーが招待できる]** を両方とも **[はい]** に設定していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-120">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="5aaf7-121">変更を加えた場合は、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-121">If you made changes, click **Save**.</span></span>

<span data-ttu-id="5aaf7-122">**[共同作業の制限]** セクションの設定に注意してください。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-122">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="5aaf7-123">共同作業するゲストのドメインがブロックされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-123">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="5aaf7-124">複数の組織のゲストと連携する場合は、ディレクトリ データにアクセスするゲストの機能を制限することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-124">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="5aaf7-125">これにより、他に誰がディレクトリ内のゲストであるかを確認できなくなります。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-125">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="5aaf7-126">これを行うには、**[ゲスト ユーザーのアクセス制限]** で、**[ゲスト ユーザーはディレクトリ オブジェクト設定のプロパティとメンバーシップに制限付きアクセス権が付与されている]** または **[ゲスト ユーザーのアクセスは自分のディレクトリ オブジェクトのプロパティとメンバーシップに制限されている]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-126">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="5aaf7-127">Teams のゲスト アクセスの設定</span><span class="sxs-lookup"><span data-stu-id="5aaf7-127">Teams guest access settings</span></span>

<span data-ttu-id="5aaf7-128">Teams には、ゲスト アクセス用のマスター オン/オフ スイッチと、ゲストがチームで実行できる操作を制御するために利用できるさまざまな設定があります。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-128">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="5aaf7-129">Teams でゲスト アクセスを機能させるには、マスター スイッチである **[Teams でゲスト アクセスを許可する]** を **[オン]** にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-129">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="5aaf7-p107">Teams でゲスト アクセスが有効になっていることを確認し、ビジネス ニーズに応じてゲスト設定を調整します。これらの設定はすべてのチームに影響することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-p107">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs. Keep in mind that these settings affect all teams.</span></span>

![Teams ゲスト アクセスのトグルのスクリーンショット](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="5aaf7-133">Teams ゲスト アクセスの設定を行うには</span><span class="sxs-lookup"><span data-stu-id="5aaf7-133">To set Teams guest access settings</span></span>

1. <span data-ttu-id="5aaf7-134">[https://admin.microsoft.com](https://admin.microsoft.com) で、Microsoft 365 管理センターにログインします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-134">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="5aaf7-135">左側のナビゲーション ウィンドウで [**すべて表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-135">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="5aaf7-136">[**管理センター**] で、[**Teams**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-136">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="5aaf7-137">Teams 管理センターの左側のナビゲーション ウィンドウで、[**組織全体の設定**] を展開して [**ゲスト アクセス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-137">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="5aaf7-138">[**Teams でのゲスト アクセスを許可する**] が [**オン**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-138">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="5aaf7-139">追加のゲスト設定に必要な変更を加えて、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-139">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

<span data-ttu-id="5aaf7-140">Teams のゲスト アクセスがオンになっている場合、機密度ラベルを使用して、個別のチームやそのチームに関連する SharePoint サイトへのゲスト アクセスを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-140">Once Teams guest access is turned on, you can optionally control guest access to individual teams and their associated SharePoint sites using sensitivity labels.</span></span> <span data-ttu-id="5aaf7-141">詳細については、「[機密ラベルを使用して、Microsoft Teams、Office 365 グループ、SharePoint サイトのコンテンツを保護する](../compliance/sensitivity-labels-teams-groups-sites.md)」 をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-141">For more information, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5aaf7-142">Teams のゲスト設定をオンにした後、有効になるまでには、最大で 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-142">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="5aaf7-143">Microsoft 365 グループのゲスト設定</span><span class="sxs-lookup"><span data-stu-id="5aaf7-143">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="5aaf7-p109">Teams は、チームのメンバーシップに Microsoft 365 グループを使用します。Teams でゲスト アクセスを機能させるには、Microsoft 365 グループのゲスト設定をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-p109">Teams uses Microsoft 365 Groups for team membership. The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Microsoft 365 管理センターにおける Microsoft 365 グループのゲスト設定のスクリーンショット](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="5aaf7-147">Microsoft 365 グループのゲスト設定を行うには</span><span class="sxs-lookup"><span data-stu-id="5aaf7-147">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="5aaf7-148">Microsoft 365 管理センターの左側のナビゲーション ウィンドウで、**[設定]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-148">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="5aaf7-149">**[組織の設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-149">Click **Org settings**.</span></span>
3. <span data-ttu-id="5aaf7-150">一覧で、**[Microsoft 365 グループ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-150">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="5aaf7-151">**[組織外のグループ所有者に Microsoft 365 グループへのアクセスを許可する]** と **[グループ メンバーにグループ コンテンツへのアクセスを許可する]** チェック ボックスが両方ともオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-151">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="5aaf7-152">変更を加えた場合は、**[変更の保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-152">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="5aaf7-153">SharePoint 組織レベルの共有設定</span><span class="sxs-lookup"><span data-stu-id="5aaf7-153">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="5aaf7-154">ファイル、フォルダー、リストなどの Teams コンテンツはすべて SharePoint に保存されます。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-154">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="5aaf7-155">ゲストが Teams でこれらのアイテムにアクセスできるようにするには、SharePoint 組織レベルの共有設定でゲストとの共有が許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-155">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="5aaf7-156">組織レベルの設定により、チームに関連付けられたサイトを含む、個々のサイトで使用できる設定が決まります。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-156">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="5aaf7-157">サイトの設定は、組織レベルの設定よりも制限を緩和することはできません。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-157">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="5aaf7-158">認証されていないユーザーとのファイルとフォルダーの共有を許可する場合は、**[全員]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-158">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="5aaf7-159">すべてのゲストが認証する必要があることを確認する場合は、**[新規および既存のゲスト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-159">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="5aaf7-160">組織内の任意のサイトで必要となる最も制限が少ない設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-160">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 組織レベルの共有設定のスクリーンショット](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="5aaf7-162">SharePoint 組織レベルの共有設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="5aaf7-162">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="5aaf7-163">Microsoft 365 管理センターの左側のナビゲーション ウィンドウの **[管理センター]** で、**[SharePoint]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-163">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="5aaf7-164">SharePoint 管理センターの左側のナビゲーション ウィンドウで、**[ポリシー]** を展開し、**[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-164">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="5aaf7-165">SharePoint の外部共有が **[全員]** または **[新規および既存のゲスト]** に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-165">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="5aaf7-166">変更を加えた場合は、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-166">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="5aaf7-167">SharePoint 組織レベルの既定のリンク設定</span><span class="sxs-lookup"><span data-stu-id="5aaf7-167">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="5aaf7-168">既定のファイルとフォルダーのリンク設定により、ファイルまたはフォルダーを共有するときに既定でユーザーに表示されるリンク オプションが決まります。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-168">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="5aaf7-169">ユーザーは、必要に応じて、共有する前に他のオプションのいずれかにリンクの種類を変更できます。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-169">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="5aaf7-170">この設定は、組織内のすべてのチームおよび SharePoint サイトに影響することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-170">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="5aaf7-171">ユーザーがファイルやフォルダーを共有する場合に既定で選択されるリンクの種類を次から 1 つ選択してください。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-171">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="5aaf7-172">**リンクを持つすべてのユーザー** - ファイルやフォルダの共有をあまり認証しないことが予想される場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-172">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="5aaf7-173">*全員* リンクを許可したいが、誤って認証されない共有が心配な場合は、他のオプションのいずれかを既定として検討してください。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-173">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="5aaf7-174">このリンクの種類は、**全員** 共有を有効にしている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-174">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="5aaf7-175">**組織内のユーザーのみ** - ほとんどのファイルとフォルダーの共有が組織内のユーザーと行われることが予想される場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-175">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="5aaf7-176">**特定のユーザー** - ゲストと多くのファイルやフォルダーを共有することが予想される場合は、このオプションを検討してください。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-176">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="5aaf7-177">この種類のリンクはゲストと連携し、ゲストに認証を要求します。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-177">This type of link works with guests and requires them to authenticate.</span></span>
 
![SharePoint 組織レベルのファイルとフォルダーの共有設定のスクリーンショット](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="5aaf7-179">SharePoint 組織レベルの既定のリンク設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="5aaf7-179">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="5aaf7-180">SharePoint 管理センターの共有ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-180">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="5aaf7-181">**ファイルとフォルダーのリンク** で、使用する既定の共有リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-181">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="5aaf7-182">変更を加えた場合は、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-182">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="5aaf7-183">チームの作成</span><span class="sxs-lookup"><span data-stu-id="5aaf7-183">Create a team</span></span>

<span data-ttu-id="5aaf7-184">次の手順は、ゲストとの共同作業に使用する予定のチームを作成することです。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-184">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="5aaf7-185">チームを作成するには</span><span class="sxs-lookup"><span data-stu-id="5aaf7-185">To create a team</span></span>
1. <span data-ttu-id="5aaf7-186">Teams の **[Teams]** タブで、左側のウィンドウの下部にある **[チームに参加またはチームを作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-186">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="5aaf7-187">**[チームを作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-187">Click **Create a team**.</span></span>
3. <span data-ttu-id="5aaf7-188">**[初めからチームを作成する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-188">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="5aaf7-189">**[プライベート]** または **[パブリック]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-189">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="5aaf7-190">チームの名前と説明を入力し、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-190">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="5aaf7-191">**[スキップ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-191">Click **Skip**.</span></span>

<span data-ttu-id="5aaf7-p116">後でユーザーを招待します。次に、チームに関連付けられている SharePoint サイトのサイトレベルの共有設定を確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-p116">We'll invite users later. Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="5aaf7-194">SharePoint のサイト レベル共有設定のスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="5aaf7-194">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="5aaf7-195">サイトレベルの共有設定をチェックして、このチームに必要な種類のアクセスが許可されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-195">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="5aaf7-196">たとえば、組織レベルの設定を **全員** に設定したが、すべてのゲストにこのチームの認証を許可する場合は、サイトレベルの共有設定が **新規および既存のゲスト** に設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-196">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![SharePoint サイトの外部共有設定のスクリーンショット](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="5aaf7-198">サイトレベルの共有設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="5aaf7-198">To set site-level sharing settings</span></span>
1. <span data-ttu-id="5aaf7-199">SharePoint 管理センターの左側のナビゲーション ウィンドウで、[**サイト**] を展開して [**アクティブなサイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-199">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="5aaf7-200">作成したチームのサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-200">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="5aaf7-201">[...] をクリックして、**共有** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-201">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="5aaf7-202">共有が **[全員]** または **[新規および既存のゲスト]** に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-202">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="5aaf7-203">変更を加えた場合は、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-203">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="5aaf7-204">ユーザーを招待する</span><span class="sxs-lookup"><span data-stu-id="5aaf7-204">Invite users</span></span>

<span data-ttu-id="5aaf7-205">ゲストの共有設定が構成されたので、チームへの内部ユーザーとゲストの追加を開始できます。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-205">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="5aaf7-206">内部ユーザーをチームに招待するには</span><span class="sxs-lookup"><span data-stu-id="5aaf7-206">To invite internal users to a team</span></span>
1. <span data-ttu-id="5aaf7-207">チームで、**[その他のオプション]** （**\*\*\***） をクリックし、**[メンバーの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-207">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="5aaf7-208">招待したい人の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-208">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="5aaf7-209">**[追加]** をクリックして、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-209">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="5aaf7-210">ゲストをチームに招待するには</span><span class="sxs-lookup"><span data-stu-id="5aaf7-210">To invite guests to a team</span></span>
1. <span data-ttu-id="5aaf7-211">チームで、**[その他のオプション]** （**\*\*\***） をクリックし、**[メンバーの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-211">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="5aaf7-212">招待したいゲストのメール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-212">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="5aaf7-213">**[ゲスト情報の編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-213">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="5aaf7-214">ゲストのフル ネームを入力し、チェック マークをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-214">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="5aaf7-215">**[追加]** をクリックして、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-215">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="5aaf7-216">関連項目</span><span class="sxs-lookup"><span data-stu-id="5aaf7-216">See also</span></span>

[<span data-ttu-id="5aaf7-217">認証されていないユーザーとファイルおよびフォルダーを共有するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="5aaf7-217">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="5aaf7-218">ゲストと共有するときにファイルの偶発的な公開を制限する</span><span class="sxs-lookup"><span data-stu-id="5aaf7-218">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="5aaf7-219">セキュリティで保護されたゲスト共有の環境を作成する</span><span class="sxs-lookup"><span data-stu-id="5aaf7-219">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="5aaf7-220">管理されたゲストで B2B エクストラネットを作成する</span><span class="sxs-lookup"><span data-stu-id="5aaf7-220">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="5aaf7-221">SharePoint および OneDrive の Azure AD B2B との統合</span><span class="sxs-lookup"><span data-stu-id="5aaf7-221">SharePoint and OneDrive integration with Azure AD B2B</span></span>](/sharepoint/sharepoint-azureb2b-integration-preview)

[<span data-ttu-id="5aaf7-222">共有オプションは、SharePoint または OneDrive から共有するときに淡色表示されます。</span><span class="sxs-lookup"><span data-stu-id="5aaf7-222">Sharing options are greyed out when sharing from SharePoint or OneDrive</span></span>](/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)