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
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Teams のゲストとの共同作業のためにチームをセットアップするために必要な Microsoft 365 の構成手順について説明します。
ms.openlocfilehash: f22404ea412085ed697f76219509c1382318e7d4
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "46797772"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="a5899-103">チームでゲストと共同で作業する</span><span class="sxs-lookup"><span data-stu-id="a5899-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="a5899-104">ドキュメント、タスク、会話でゲストと共同作業を行う必要がある場合は、Microsoft Teams を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a5899-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="a5899-105">Teams は、常設チャットと、カスタマイズ可能で拡張可能なコラボレーションツールのセットを統合されたユーザーの環境で使用できる、Office および SharePoint で利用可能なすべてのコラボレーション機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="a5899-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="a5899-106">この記事では、ゲストとの共同作業のためにチームをセットアップするために必要な Microsoft 365 の構成手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5899-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="a5899-107">ビデオ デモンストレーション</span><span class="sxs-lookup"><span data-stu-id="a5899-107">Video demonstration</span></span>

<span data-ttu-id="a5899-108">このビデオでは、このドキュメントで説明されている構成手順を示します。</span><span class="sxs-lookup"><span data-stu-id="a5899-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="a5899-109">Azure の組織上の関係の設定</span><span class="sxs-lookup"><span data-stu-id="a5899-109">Azure Organizational relationships settings</span></span>

<span data-ttu-id="a5899-110">Microsoft 365 での共有は、 [Azure Active Directory の組織上の関係の設定](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)によって最上位レベルで管理されます。</span><span class="sxs-lookup"><span data-stu-id="a5899-110">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="a5899-111">Azure AD でゲストの共有が無効または制限されている場合、これは Microsoft 365 で構成した共有設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="a5899-111">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="a5899-112">組織上の関係の設定を確認して、ゲストとの共有がブロックされないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="a5899-112">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Azure Active Directory における組織の関係の設定ページのスクリーンショット](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="a5899-114">組織上の関係の設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="a5899-114">To set organizational relationship settings</span></span>

1. <span data-ttu-id="a5899-115">Microsoft Azure にログイン [https://portal.azure.com](https://portal.azure.com) します。</span><span class="sxs-lookup"><span data-stu-id="a5899-115">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="a5899-116">左側のナビゲーションで、[ **Azure Active Directory**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-116">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="a5899-117">[**概要**] ウィンドウで、[**外部 ID**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-117">In the **Overview** pane, click **External identities**.</span></span>
4. <span data-ttu-id="a5899-118">[ **組織の id** ] ウィンドウで、[ **外部グループ作業の設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-118">In the **Organizational identities** pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="a5899-119">**管理者とゲスト招待元役割のユーザーが招待できる**ことと、**メンバーが招待**できることを確認します。どちらも **[はい]** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="a5899-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="a5899-120">変更を加えた場合は、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="a5899-121">[ **共同作業の制限** ] セクションの設定に注意してください。</span><span class="sxs-lookup"><span data-stu-id="a5899-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="a5899-122">共同作業を行うゲストのドメインがブロックされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5899-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="a5899-123">複数の組織のゲストを使用している場合は、ディレクトリデータへのアクセスを制限することをお客様に許可します。</span><span class="sxs-lookup"><span data-stu-id="a5899-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="a5899-124">これにより、他のユーザーがディレクトリ内のゲストであることを確認できなくなります。</span><span class="sxs-lookup"><span data-stu-id="a5899-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="a5899-125">これを行うには、[ **ゲストユーザーのアクセス制限**] で、[ゲストユーザー **がアクセスを制限しているのは、ディレクトリオブジェクトのプロパティとメンバーシップ] 設定** または **guest ユーザーアクセスが、自分のディレクトリオブジェクトのプロパティとメンバーシップに制限され**ています。</span><span class="sxs-lookup"><span data-stu-id="a5899-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="a5899-126">Teams ゲストアクセス設定</span><span class="sxs-lookup"><span data-stu-id="a5899-126">Teams guest access settings</span></span>

<span data-ttu-id="a5899-127">Teams には、ゲストアクセス用のマスターオン/オフスイッチ、およびチーム内でゲストが実行できることを制御するさまざまな設定があります。</span><span class="sxs-lookup"><span data-stu-id="a5899-127">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="a5899-128">Teams でゲストアクセスを有効にする**には、** マスタースイッチで、 **teams でゲストアクセスを許可**する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5899-128">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="a5899-129">Teams でゲストアクセスが有効になっていることを確認し、ビジネスニーズに基づいてゲスト設定を調整してください。</span><span class="sxs-lookup"><span data-stu-id="a5899-129">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="a5899-130">これらの設定はすべてのチームに影響を与えることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a5899-130">Keep in mind that these settings affect all teams.</span></span>

![Teams ゲスト アクセスのトグルのスクリーンショット](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="a5899-132">Teams ゲスト アクセスの設定を行うには</span><span class="sxs-lookup"><span data-stu-id="a5899-132">To set Teams guest access settings</span></span>

1. <span data-ttu-id="a5899-133">[https://admin.microsoft.com](https://admin.microsoft.com) で、Microsoft 365 管理センターにログインします。</span><span class="sxs-lookup"><span data-stu-id="a5899-133">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="a5899-134">左側のナビゲーションで [**すべて表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-134">In the left navigation, click **Show all**.</span></span>
3. <span data-ttu-id="a5899-135">[**管理センター**] で、[**Teams**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-135">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="a5899-136">Teams 管理センターの左側のナビゲーションで、[**組織全体の設定**] を展開して [**ゲスト アクセス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-136">In the Teams admin center, in the left navigation, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="a5899-137">[**Teams でのゲスト アクセスを許可する**] が [**オン**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5899-137">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="a5899-138">追加のゲスト設定に必要な変更を加えて、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-138">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="a5899-139">Teams のゲスト設定をオンにした後、有効になるまでには、最大で 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a5899-139">It may take up to twenty-four hours for the Teams guest setting to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="a5899-140">Microsoft 365 グループのゲスト設定</span><span class="sxs-lookup"><span data-stu-id="a5899-140">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="a5899-141">Teams では、チームメンバーシップに Microsoft 365 グループを使用します。</span><span class="sxs-lookup"><span data-stu-id="a5899-141">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="a5899-142">Teams でゲストアクセスを機能させるには、Microsoft 365 Groups のゲスト設定をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5899-142">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Microsoft 365 管理センターにおける Microsoft 365 グループのゲスト設定のスクリーンショット](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="a5899-144">Microsoft 365 グループのゲスト設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="a5899-144">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="a5899-145">Microsoft 365 管理センターの左側のナビゲーションで、[ **設定**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="a5899-145">In the Microsoft 365 admin center, in the left navigation, expand **Settings**.</span></span>
2. <span data-ttu-id="a5899-146">[ **組織の設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-146">Click **Org settings**.</span></span>
3. <span data-ttu-id="a5899-147">一覧で、[ **Microsoft 365 Groups**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-147">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="a5899-148">[組織外のユーザーにグループの **コンテンツへのアクセス** を許可する] および [ **グループの所有者に組織外のユーザーをグループに追加する** ] チェックボックスの両方がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5899-148">Ensure that the **Let group members outside your organization access group content** and **Let group owners add people outside your organization to groups** check boxes are both checked.</span></span>
5. <span data-ttu-id="a5899-149">変更を加えた場合は、[ **変更の保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-149">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="a5899-150">SharePoint 組織レベルの共有設定</span><span class="sxs-lookup"><span data-stu-id="a5899-150">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="a5899-151">ファイル、フォルダー、リストなどの Teams コンテンツはすべて SharePoint に格納されます。</span><span class="sxs-lookup"><span data-stu-id="a5899-151">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="a5899-152">ゲストがこれらのアイテムに Teams でアクセスできるようにするには、SharePoint の組織レベルの共有設定でゲストとの共有が許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5899-152">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="a5899-153">組織レベルの設定は、teams に関連付けられたサイトを含む、個々のサイトで使用可能な設定を決定します。</span><span class="sxs-lookup"><span data-stu-id="a5899-153">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="a5899-154">サイトの設定は、組織レベルの設定よりも制限することはできません。</span><span class="sxs-lookup"><span data-stu-id="a5899-154">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="a5899-155">認証されていないユーザーとのファイルとフォルダーの共有を許可する場合は、[ **すべて**のユーザー] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5899-155">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="a5899-156">すべてのゲストが認証を必要とするようにするには、[ **新規および既存のゲスト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5899-156">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="a5899-157">組織内のすべてのサイトで必要とされる最も厳しい設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5899-157">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 組織レベルの共有設定のスクリーンショット](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="a5899-159">SharePoint 組織レベルの共有設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="a5899-159">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="a5899-160">Microsoft 365 管理センターで、左側のナビゲーションの [ **管理センター**] の下にある [ **SharePoint**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-160">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="a5899-161">SharePoint 管理センターの左側のナビゲーションで、**[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-161">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="a5899-162">SharePoint の外部共有が [ **すべてのユーザー** ] または **[既存のゲスト**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5899-162">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="a5899-163">変更を加えた場合は、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-163">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="a5899-164">SharePoint 組織レベルの既定のリンク設定</span><span class="sxs-lookup"><span data-stu-id="a5899-164">SharePoint organization level default link settings</span></span>

<span data-ttu-id="a5899-165">既定のファイルとフォルダーのリンク設定によって、ユーザーがファイルまたはフォルダーを共有するときに、どのリンクオプションが既定で表示されるかが決まります。</span><span class="sxs-lookup"><span data-stu-id="a5899-165">The default file and folder link settings determine which link option is shown to the user by default when they share a file or folder.</span></span> <span data-ttu-id="a5899-166">ユーザーは、必要に応じて、共有する前に、リンクの種類を他のオプションのいずれかに変更できます。</span><span class="sxs-lookup"><span data-stu-id="a5899-166">Users can change the link type to one of the other options before sharing if desired.</span></span>

<span data-ttu-id="a5899-167">この設定は、組織内のすべての teams および SharePoint サイトに影響を与えることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a5899-167">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="a5899-168">ユーザーがファイルやフォルダーを共有するときに既定で選択されるリンクの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5899-168">Choose the type of link that's selected by default when users share files and folders:</span></span>

- <span data-ttu-id="a5899-169">**リンクを持つすべてのユーザー** -ファイルとフォルダーの認証されていない共有を頻繁に行う場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a5899-169">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="a5899-170">*すべて*のリンクを許可し、偶発的な認証されていない共有について懸念している場合は、他のオプションのいずれかを既定値として検討します。</span><span class="sxs-lookup"><span data-stu-id="a5899-170">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="a5899-171">このリンクの種類は、 **すべて** の共有を有効にした場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a5899-171">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="a5899-172">[**組織内のユーザーのみ**]-ほとんどのファイルとフォルダーの共有が組織内のユーザーと想定される場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a5899-172">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="a5899-173">**特定のユーザー** -多数のファイルとフォルダーをゲストで共有することが予想される場合は、このオプションを検討してください。</span><span class="sxs-lookup"><span data-stu-id="a5899-173">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="a5899-174">この種類のリンクはゲストと連動しており、認証を必要とします。</span><span class="sxs-lookup"><span data-stu-id="a5899-174">This type of link works with guests and requires them to authenticate.</span></span>
 
![SharePoint における組織レベルのファイルとフォルダー設定のスクリーンショット](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="a5899-176">SharePoint 組織レベルの既定のリンク設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="a5899-176">To set the SharePoint organization level default link settings</span></span>

1. <span data-ttu-id="a5899-177">SharePoint 管理センターの [共有] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="a5899-177">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="a5899-178">[ **ファイルとフォルダーのリンク**] で、使用する既定の共有リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="a5899-178">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="a5899-179">変更を加えた場合は、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-179">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="a5899-180">チームを作成する</span><span class="sxs-lookup"><span data-stu-id="a5899-180">Create a team</span></span>

<span data-ttu-id="a5899-181">次の手順では、ゲストとの共同作業に使用する予定のチームを作成します。</span><span class="sxs-lookup"><span data-stu-id="a5899-181">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="a5899-182">チームを作成するには</span><span class="sxs-lookup"><span data-stu-id="a5899-182">To create a team</span></span>
1. <span data-ttu-id="a5899-183">Teams の [ **teams** ] タブで、左側のウィンドウの下部にある [ **参加] または [チームの作成** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-183">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="a5899-184">[ **チームの作成] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-184">Click **Create a team**.</span></span>
3. <span data-ttu-id="a5899-185">[ **チームの新規作成] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-185">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="a5899-186">[ **プライベート** ] または [ **パブリック**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5899-186">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="a5899-187">チームの名前と説明を入力し、[ **作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-187">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="a5899-188">[ **スキップ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-188">Click **Skip**.</span></span>

<span data-ttu-id="a5899-189">後でユーザーを招待します。</span><span class="sxs-lookup"><span data-stu-id="a5899-189">We'll invite users later.</span></span> <span data-ttu-id="a5899-190">次に、チームに関連付けられている SharePoint サイトのサイトレベルでの共有設定を確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="a5899-190">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="a5899-191">SharePoint サイトレベルの共有設定</span><span class="sxs-lookup"><span data-stu-id="a5899-191">SharePoint site level sharing settings</span></span>

<span data-ttu-id="a5899-192">サイトレベルの共有設定をチェックして、このチームに必要なアクセスの種類が許可されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a5899-192">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="a5899-193">たとえば、組織レベルの設定をすべての **ユーザー**に設定しているが、すべてのゲストがこのチームの認証を必要とする場合は、サイトレベルの共有設定が **新規および既存のゲスト**に設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a5899-193">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![SharePoint サイトの外部共有設定のスクリーンショット](../media/sharepoint-site-external-sharing-settings.png)


<span data-ttu-id="a5899-195">サイトレベルの共有設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="a5899-195">To set site-level sharing settings</span></span>
1. <span data-ttu-id="a5899-196">SharePoint 管理センターの左側のナビゲーションで、[**サイト**] を展開して [**アクティブなサイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-196">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="a5899-197">作成したチームのサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="a5899-197">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="a5899-198">リボンで [**共有**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-198">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="a5899-199">共有が [ **すべてのユーザー** ] または **[既存のゲスト**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5899-199">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="a5899-200">変更を加えた場合は、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-200">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="a5899-201">ユーザーを招待する</span><span class="sxs-lookup"><span data-stu-id="a5899-201">Invite users</span></span>

<span data-ttu-id="a5899-202">これでゲスト共有の設定が構成されるようになり、チームへの内部ユーザーとゲストの追加を開始できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a5899-202">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="a5899-203">内部ユーザーをチームに招待するには</span><span class="sxs-lookup"><span data-stu-id="a5899-203">To invite internal users to a team</span></span>
1. <span data-ttu-id="a5899-204">チームで、[ **その他のオプション** ] () をクリックし、[ **\*\*\*** メンバーの **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-204">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="a5899-205">招待するユーザーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a5899-205">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="a5899-206">**[追加]** をクリックして、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-206">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="a5899-207">ゲストをチームに招待するには</span><span class="sxs-lookup"><span data-stu-id="a5899-207">To invite guests to a team</span></span>
1. <span data-ttu-id="a5899-208">チームで、[ **その他のオプション** ] () をクリックし、[ **\*\*\*** メンバーの **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-208">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="a5899-209">招待するゲストの電子メールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="a5899-209">Type the email address of the guest who you want to invite.</span></span>
3. <span data-ttu-id="a5899-210">[ **ゲスト情報の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-210">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="a5899-211">ゲストの完全な名前を入力し、チェックマークをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-211">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="a5899-212">**[追加]** をクリックして、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5899-212">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5899-213">関連項目</span><span class="sxs-lookup"><span data-stu-id="a5899-213">See Also</span></span>

[<span data-ttu-id="a5899-214">認証されていないユーザーとファイルおよびフォルダーを共有するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="a5899-214">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="a5899-215">ゲストと共有するときにファイルの偶発的な公開を制限する</span><span class="sxs-lookup"><span data-stu-id="a5899-215">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="a5899-216">セキュリティで保護されたゲスト共有環境を作成する</span><span class="sxs-lookup"><span data-stu-id="a5899-216">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="a5899-217">管理されたゲストで B2B エクストラネットを作成する</span><span class="sxs-lookup"><span data-stu-id="a5899-217">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)
