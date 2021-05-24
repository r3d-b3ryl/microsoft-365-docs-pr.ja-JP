---
title: Microsoft 365 の共有を制限する
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
search.appverid:
- SPO160
- MET150
f1.keywords: NOCSH
ms.custom: ''
localization_priority: Priority
recommendations: false
description: Microsoft 365 で共有を制限または無効にするオプションについて説明します。
ms.openlocfilehash: f237df883bb401342a3a5c93432beeb5028cfce6
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539193"
---
# <a name="limit-sharing-in-microsoft-365"></a><span data-ttu-id="c7f46-103">Microsoft 365 の共有を制限する</span><span class="sxs-lookup"><span data-stu-id="c7f46-103">Limit sharing in Microsoft 365</span></span>

<span data-ttu-id="c7f46-104">内部共有を完全に無効にすることや、サイトから [共有] ボタンを削除することはできませんが、組織のニーズを満たすように Microsoft 365 の共有を制限する方法は多数あります。</span><span class="sxs-lookup"><span data-stu-id="c7f46-104">While you can't disable internal sharing entirely or remove the Share button from sites, there are a variety of ways that you can limit sharing in Microsoft 365 to meet the needs of your organization.</span></span>

<span data-ttu-id="c7f46-105">次の表に、ファイルの共有方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c7f46-105">The methods of sharing files are listed in the table below.</span></span> <span data-ttu-id="c7f46-106">詳細については、「**共有方法**」列のリンクをクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="c7f46-106">Click the link in the **Sharing method** column for detailed information.</span></span>

|<span data-ttu-id="c7f46-107">共有方法</span><span class="sxs-lookup"><span data-stu-id="c7f46-107">Sharing method</span></span>|<span data-ttu-id="c7f46-108">説明</span><span class="sxs-lookup"><span data-stu-id="c7f46-108">Description</span></span>|<span data-ttu-id="c7f46-109">制限のオプション</span><span class="sxs-lookup"><span data-stu-id="c7f46-109">Limiting options</span></span>|
|:-------------|:----------|:-------------|
|[<span data-ttu-id="c7f46-110">Microsoft 365 グループまたはチーム</span><span class="sxs-lookup"><span data-stu-id="c7f46-110">Microsoft 365 group or team</span></span>](#microsoft-365-group-or-team)|<span data-ttu-id="c7f46-111">Microsoft Teams チームまたは Microsoft 365 グループへのアクセスを許可されているユーザーは、関連付けられた SharePoint サイトのファイルに対する編集アクセス許可を持ちます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-111">People granted access to a Microsoft Teams team or Microsoft 365 group have edit access to files in the associated SharePoint site.</span></span>|<span data-ttu-id="c7f46-112">グループまたはチームがプライベートの場合は、チームに参加するための共有の招待は承認を得るために所有者に回送されます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-112">If the group or team is private, sharing invitations to join the team go to the owner for approval.</span></span> <span data-ttu-id="c7f46-113">管理者は、ゲスト アクセスを無効にするか、秘密度ラベルを使用して、組織の部外者からのアクセスを禁止することができます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-113">Admins can disable guest access or use sensitivity labels to prevent access by people from outside the organization.</span></span>|
|[<span data-ttu-id="c7f46-114">SharePoint サイト</span><span class="sxs-lookup"><span data-stu-id="c7f46-114">SharePoint site</span></span>](#sharepoint-site)|<span data-ttu-id="c7f46-115">ユーザーには SharePoint サイトに対する所有者、メンバー、または閲覧者のアクセス権を付与できます。ユーザーは、サイト内のファイルに対して、そのレベルに応じたアクセス権を持ちます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-115">People can be granted Owner, Member, or Visitor access to a SharePoint site and will have that level of access to files in the site.</span></span>|<span data-ttu-id="c7f46-116">サイトのアクセス許可は、サイトの所有者のみがサイトの共有を可能にするように制限できます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-116">Site permissions can be restricted so that only site owners can share the site.</span></span> <span data-ttu-id="c7f46-117">管理者は、サイトを読み取り専用に設定するか、アクセスを完全にブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-117">Admins can set a site to read-only or block access entirely.</span></span>|
|[<span data-ttu-id="c7f46-118">特定のユーザーとの共有</span><span class="sxs-lookup"><span data-stu-id="c7f46-118">Sharing with specific people</span></span>](#sharing-with-specific-people)|<span data-ttu-id="c7f46-119">サイトのメンバーと編集アクセス許可を持つユーザーは、*特定のユーザー* リンクを使用することで、ファイルおよびフォルダーへの直接のアクセス許可を付与することや共有することができます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-119">Site members and people with edit permissions can give direct permissions to files and folders or share them by using *Specific people* links.</span></span>|<span data-ttu-id="c7f46-120">サイトのアクセス許可は、サイトの所有者のみがファイルおよびフォルダーの共有を可能にするように制限できます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-120">Site permissions can be restricted so that only site owners can share files and folders.</span></span> <span data-ttu-id="c7f46-121">この場合、サイトのメンバーによる直接アクセス権および *特定のユーザー* リンクの共有は、承認を得るためにサイト所有者に回送されます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-121">In this case, direct access and *Specific people* link sharing by site members goes to site owner for approval.</span></span>|
|[<span data-ttu-id="c7f46-122">SharePoint と OneDrive のゲスト共有</span><span class="sxs-lookup"><span data-stu-id="c7f46-122">SharePoint and OneDrive guest sharing</span></span>](#sharepoint-guest-sharing)|<span data-ttu-id="c7f46-123">SharePoint サイトの所有者とメンバー、および OneDrive の所有者は、組織外のユーザーとファイルおよびフォルダーを共有できます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-123">SharePoint site owners and members and OneDrive owners can share files and folders with people outside the organization.</span></span>|<span data-ttu-id="c7f46-124">ゲスト共有は組織全体または個別のサイトごとに無効化できます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-124">Guest sharing can be disabled for the entire organization or for individual sites.</span></span>|
|[<span data-ttu-id="c7f46-125">*組織内のユーザー* 共有リンク</span><span class="sxs-lookup"><span data-stu-id="c7f46-125">*People in your organization* sharing links</span></span>](#people-in-your-organization-sharing-links)|<span data-ttu-id="c7f46-126">SharePoint サイトの所有者とメンバーは、*組織内のユーザー* リンクを使用することでファイルを共有できます。このリンクは、組織内のすべてのユーザーに対して機能します。</span><span class="sxs-lookup"><span data-stu-id="c7f46-126">SharePoint site owners and members can share files using *People in your organization* links, which will work for anyone inside the organization.</span></span>|<span data-ttu-id="c7f46-127">*組織内のユーザー* リンクは、サイト レベルで無効化できます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-127">*People in your organization* links can be disabled at the site level.</span></span>|
|[<span data-ttu-id="c7f46-128">サイト、グループ、チームを作成する</span><span class="sxs-lookup"><span data-stu-id="c7f46-128">Create sites, groups, and teams</span></span>](#create-sites-groups-and-teams)|<span data-ttu-id="c7f46-129">既定では、ユーザーはコンテンツを共有できる新しいサイト、グループ、およびチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-129">By default, users can create new sites, groups, and teams from which they can share content.</span></span>|<span data-ttu-id="c7f46-130">管理者は、サイト、グループ、およびチームを作成できるユーザーを制限できます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-130">Admins can restrict who can create sites, groups, and teams.</span></span>|
|[<span data-ttu-id="c7f46-131">電子メール</span><span class="sxs-lookup"><span data-stu-id="c7f46-131">Email</span></span>](#email)|<span data-ttu-id="c7f46-132">ファイルにアクセスできるユーザーは、そのファイルを電子メールで別のユーザーに送信できます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-132">People with access to a file can send it to others via email.</span></span>|<span data-ttu-id="c7f46-133">管理者は、秘密度ラベルを使用してファイルを暗号化することで、許可されていないユーザーとのファイルの共有を防止できます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-133">Admins can encrypt files by using sensitivity labels to prevent them being shared with unauthorized people.</span></span>|
|[<span data-ttu-id="c7f46-134">ダウンロードまたはファイルのコピー</span><span class="sxs-lookup"><span data-stu-id="c7f46-134">Download or file copy</span></span>](#download-or-file-copy)|<span data-ttu-id="c7f46-135">ファイルにアクセスできるユーザーは、ファイルをダウンロードまたはコピーして Microsoft 365 の適用範囲外のユーザーと共有できます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-135">People with access to a file can download or copy it and share it with others outside the scope of Microsoft 365.</span></span>|<span data-ttu-id="c7f46-136">管理者は、秘密度ラベルを使用してファイルを暗号化することで、許可されていないユーザーとのファイルの共有を防止できます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-136">Admins can encrypt files by using sensitivity labels to prevent them being shared with unauthorized people.</span></span>|

<span data-ttu-id="c7f46-137">ユーザーが共有コンテンツにアクセスする条件を制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-137">You can also restrict the conditions under which people access shared content.</span></span> <span data-ttu-id="c7f46-138">詳細については、この記事で後述する [条件付きアクセス](#conditional-access) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7f46-138">See [conditional access](#conditional-access) later in this article for more information.</span></span>

<span data-ttu-id="c7f46-139">組織内の共有は、この記事で説明する管理者コントロールを使用して制限できますが、安全な共有環境を作成するために Microsoft 365 で使用可能なセキュリティとコンプライアンスの機能を使用することを検討するようお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-139">While you can use the admin controls described in this article to limit sharing in your organization, we highly recommend that you consider using the security and compliance features available in Microsoft 365 to create a secure sharing environment.</span></span> <span data-ttu-id="c7f46-140">詳細については、「[Microsoft 365 による SharePoint のファイルの共同作業](/sharepoint/deploy-file-collaboration)」および「[セキュリティの分離を使用してチームを構成する](secure-teams-security-isolation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7f46-140">See [File collaboration in SharePoint with Microsoft 365](/sharepoint/deploy-file-collaboration) and [Configure a team with security isolation](secure-teams-security-isolation.md) for information.</span></span>

<span data-ttu-id="c7f46-141">組織内で使用されている共有方法を理解するには、[ファイルとフォルダーの共有に関するレポートを実行](/sharepoint/sharing-reports)してください。</span><span class="sxs-lookup"><span data-stu-id="c7f46-141">To understand how sharing is being used in your organization, [run a report on file and folder sharing](/sharepoint/sharing-reports).</span></span>

## <a name="microsoft-365-group-or-team"></a><span data-ttu-id="c7f46-142">Microsoft 365 グループまたはチーム</span><span class="sxs-lookup"><span data-stu-id="c7f46-142">Microsoft 365 group or team</span></span>

<span data-ttu-id="c7f46-143">Microsoft 365 グループまたは Microsoft Teams チームで共有を制限する場合は、グループまたはチームをプライベートにすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="c7f46-143">If you want to limit sharing in a Microsoft 365 group or Microsoft Teams team, it's important to make the group or team private.</span></span> <span data-ttu-id="c7f46-144">組織内のユーザーは、パブリック グループまたはチームにいつでも参加できます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-144">People inside your organization can join a public group or team anytime.</span></span> <span data-ttu-id="c7f46-145">グループまたはチームをプライベートにしていないと、チームの共有またはそのファイルの組織内での共有を制限する方法がなくなります。</span><span class="sxs-lookup"><span data-stu-id="c7f46-145">Unless the group or team is private, there's no way to limit sharing of the team or its files within the organization.</span></span>

### <a name="guest-sharing"></a><span data-ttu-id="c7f46-146">ゲスト共有</span><span class="sxs-lookup"><span data-stu-id="c7f46-146">Guest sharing</span></span>

<span data-ttu-id="c7f46-147">Teams のゲスト アクセスを禁止する場合は、Teams 管理センターでゲスト共有をオフにします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-147">If you want to prevent guest access in Teams, you can turn off guest sharing in the Teams admin center.</span></span>

<span data-ttu-id="c7f46-148">Teams のゲスト共有をオフにするには</span><span class="sxs-lookup"><span data-stu-id="c7f46-148">To turn off guest sharing for Teams</span></span>
1. <span data-ttu-id="c7f46-149">Teams 管理センターで、**[組織全体の設定]** を展開して **[ゲスト アクセス]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-149">In the Teams admin center, expand **Org-wide settings**, and then click **Guest access**.</span></span>
2. <span data-ttu-id="c7f46-150">**[Teams のゲスト アクセスを許可する]** をオフにします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-150">Turn off **Allow guest access in Teams**.</span></span>
3. <span data-ttu-id="c7f46-151">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-151">Click **Save**.</span></span>

<span data-ttu-id="c7f46-152">Microsoft 365 グループのゲスト アクセスを禁止する場合は、Microsoft 365 管理センターでグループのゲスト アクセス設定をオフにします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-152">If you want to prevent guest access in Microsoft 365 Groups, you can turn off the groups guest access settings in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="c7f46-153">Microsoft 365 グループのゲスト共有をオフにするには</span><span class="sxs-lookup"><span data-stu-id="c7f46-153">To turn off guest sharing in Microsoft 365 Groups</span></span>
1. <span data-ttu-id="c7f46-154">Microsoft 365 管理センターで、**[設定]** をクリックしてから **[組織の設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-154">In the Microsoft 365 admin center, click **Settings**, and then click **Org Settings**.</span></span>
2. <span data-ttu-id="c7f46-155">**[サービス]** タブで、**[Microsoft 365 Groups](Microsoft 365 グループ)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-155">On the **Services** tab, click **Microsoft 365 Groups**.</span></span>
3. <span data-ttu-id="c7f46-156">チェックボックスの **[組織外のグループ メンバーがグループ コンテンツにアクセスできるようにします]** と **[グループの所有者が組織外のユーザーをグループに追加できるようにします]** をオフにします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-156">Clear the **Let group members outside your organization access group content** and **Let group owners add people outside your organization to groups** check boxes.</span></span>
4. <span data-ttu-id="c7f46-157">**[変更の保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-157">Click **Save changes**.</span></span>

    ![Microsoft 365 管理センターの Microsoft 365 グループ共有設定のスクリーンショット](../media/office-365-groups-guest-settings-off.png)

> [!NOTE]
> <span data-ttu-id="c7f46-159">特定のグループまたはチームのゲスト共有を禁止する場合には、[Microsoft PowerShell](per-group-guest-access.md) または [秘密度ラベル](../compliance/sensitivity-labels-teams-groups-sites.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c7f46-159">If you want to prevent guest sharing for a particular group or team, you can do so by using [Microsoft PowerShell](per-group-guest-access.md) or [sensitivity labels](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

<span data-ttu-id="c7f46-160">特定のドメインのユーザーに対するゲスト共有は、Azure Active Directory でドメインを許可またはブロックすることで制限できます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-160">You can limit guest sharing to users from specific domains by allowing or blocking domains in Azure Active Directory.</span></span> <span data-ttu-id="c7f46-161">[SharePoint および OneDrive の Azure AD B2B との統合](/sharepoint/sharepoint-azureb2b-integration-preview)を有効にしている場合、この制限は SharePoint のゲスト共有にも影響します。</span><span class="sxs-lookup"><span data-stu-id="c7f46-161">This will also affect guest sharing in SharePoint if you have enabled [SharePoint and OneDrive integration with Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview).</span></span>

<span data-ttu-id="c7f46-162">特定のドメインからの共有招待状のみを許可するには</span><span class="sxs-lookup"><span data-stu-id="c7f46-162">To allow sharing invitations only from specified domains</span></span>
1. <span data-ttu-id="c7f46-163">Azure Active Directory の [概要] ページで、**[組織の関係]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-163">In Azure Active Directory, on the Overview page, click **Organizational relationships**.</span></span>
2. <span data-ttu-id="c7f46-164">**[設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-164">Click **Settings**.</span></span>
3. <span data-ttu-id="c7f46-165">**[コラボレーションの制限]** の下側にある **[指定したドメインのへの招待を拒否します]** または **[指定したドメインに対してのみ招待を許可します]** を選択して、その設定に使用するドメインを入力します。</span><span class="sxs-lookup"><span data-stu-id="c7f46-165">Under **Collaboration restrictions**, select **Deny invitations to the specified domains** or **Allow invitations only to the specified domains**, and then type the domains that you want to use.</span></span>
4. <span data-ttu-id="c7f46-166">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-166">Click **Save**.</span></span>

    ![Azure Active Directory の [コラボレーションの制限] 設定のスクリーンショット](../media/azure-ad-allow-only-specified-domains.png)

## <a name="sharepoint-site"></a><span data-ttu-id="c7f46-168">SharePoint サイト</span><span class="sxs-lookup"><span data-stu-id="c7f46-168">SharePoint site</span></span>

<span data-ttu-id="c7f46-169">SharePoint サイトの共有は、サイト所有者のみに制限できます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-169">You can limit SharePoint site sharing to site owners only.</span></span> <span data-ttu-id="c7f46-170">これにより、サイト メンバーはサイトの共有ができなくなります。</span><span class="sxs-lookup"><span data-stu-id="c7f46-170">This prevents site members from sharing the site.</span></span> <span data-ttu-id="c7f46-171">サイトが Microsoft 365 グループに接続されていると、グループ メンバーは別のユーザーをグループに招待でき、そのように招待したユーザーはサイトにアクセスできるようになる点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c7f46-171">Keep in mind that if the site is connected to a Microsoft 365 group, group members can invite others to the group and those users will have site access.</span></span>

<span data-ttu-id="c7f46-172">サイト共有を所有者に制限するには</span><span class="sxs-lookup"><span data-stu-id="c7f46-172">To limit site sharing to owners</span></span>
1. <span data-ttu-id="c7f46-173">サイトにある歯車アイコンをクリックして、**[サイトの権限]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-173">In the site, click the gear icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="c7f46-174">**[共有の設定]** の下側にある **[共有設定を変更します]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-174">Under **Sharing settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="c7f46-175">**[サイトの所有者とメンバー、および編集アクセス許可を持つユーザーは、ファイルとフォルダーを共有できますが、サイトの所有者のみがサイトを共有できます]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7f46-175">Select **Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**.</span></span>
4. <span data-ttu-id="c7f46-176">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-176">Click **Save**.</span></span>

    ![SharePoint サイトの [共有アクセス許可] 設定のスナップショット](../media/sharepoint-site-sharing-permissions-level-two.png)

<span data-ttu-id="c7f46-178">サイトのメンバー以外のユーザーによるアクセスの要求は、アクセス要求をオフにすることで禁止できます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-178">You can prevent users who are not members of the site from requesting access by turning off access requests.</span></span>

<span data-ttu-id="c7f46-179">アクセス要求をオフにするには</span><span class="sxs-lookup"><span data-stu-id="c7f46-179">To turn off access requests</span></span>
1. <span data-ttu-id="c7f46-180">サイトにある歯車アイコンをクリックして、**[サイトの権限]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-180">In the site, click the gear icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="c7f46-181">**[共有の設定]** の下側にある **[共有設定を変更します]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-181">Under **Sharing settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="c7f46-182">**[アクセス要求の許可]** をオフにして、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-182">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="c7f46-183">サイトの共有は、そのサイトに対してドメインを許可またはブロックすることで特定のドメインに制限できます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-183">You can limit site sharing to specific domains by allowing or blocking domains for the site.</span></span>

<span data-ttu-id="c7f46-184">ドメイン単位でサイトの共有を制限するには</span><span class="sxs-lookup"><span data-stu-id="c7f46-184">To limit site sharing by domain</span></span>
1. <span data-ttu-id="c7f46-185">SharePoint 管理センターで、**[サイト]** の下側にある **[アクティブなサイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-185">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="c7f46-186">構成するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-186">Click the site that you want to configure.</span></span>
3. <span data-ttu-id="c7f46-187">**[ポリシー]** タブで、**[外部共有]** の下側にある **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-187">On the **Policies** tab, under **External sharing** click **Edit**.</span></span>
4. <span data-ttu-id="c7f46-188">**[外部共有の詳細設定]** の下側にある **[ドメインで外部共有を制限する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7f46-188">Under **Advanced settings for external sharing**, select the **Limit sharing by domain**.</span></span>
5. <span data-ttu-id="c7f46-189">許可またはブロックするドメインを追加して、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-189">Add the domains that you want to allow or block, and then click **Save**.</span></span>
6. <span data-ttu-id="c7f46-190">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-190">Click **Save**.</span></span>

    ![許可されたドメインのサイトレベル設定のスクリーンショット](../media/limit-site-sharing-by-domain.png)

### <a name="block-access-to-a-site"></a><span data-ttu-id="c7f46-192">サイトへのアクセスの禁止</span><span class="sxs-lookup"><span data-stu-id="c7f46-192">Block access to a site</span></span>

<span data-ttu-id="c7f46-193">サイトのロック状態を変更することで、サイトへのアクセスをブロックしたり、サイトを読み取り専用にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-193">You can block access to a site or make a site read-only by changing the lock state of the site.</span></span> <span data-ttu-id="c7f46-194">詳細については、「[サイトのロックとロック解除](/sharepoint/manage-lock-status)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7f46-194">For details, see [Lock and unlock sites](/sharepoint/manage-lock-status).</span></span>

### <a name="permissions-inheritance"></a><span data-ttu-id="c7f46-195">アクセス許可の継承</span><span class="sxs-lookup"><span data-stu-id="c7f46-195">Permissions inheritance</span></span>

<span data-ttu-id="c7f46-196">推奨されていませんが、 [SharePoint アクセス許可の継承](/sharepoint/what-is-permissions-inheritance) を使用して、サイトやサブサイトのアクセス レベルをカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-196">While not recommended, you can use [SharePoint permissions inheritance](/sharepoint/what-is-permissions-inheritance) to customize access levels to sites and subsites.</span></span>

## <a name="sharing-with-specific-people"></a><span data-ttu-id="c7f46-197">特定のユーザーとの共有</span><span class="sxs-lookup"><span data-stu-id="c7f46-197">Sharing with specific people</span></span>

<span data-ttu-id="c7f46-198">サイトまたはそのコンテンツの共有を制限する場合は、サイト所有者のみがファイル、フォルダー、およびサイトを共有できるようにサイトを構成します。</span><span class="sxs-lookup"><span data-stu-id="c7f46-198">if you want to limit the sharing of a site or its contents, you can configure the site to only allow site owners to share files, folders, and the site.</span></span> <span data-ttu-id="c7f46-199">このように構成すると、サイト メンバーが *特定のユーザー* リンクを使用してファイルやフォルダーを共有しようとしたときに、その操作は承認を得るためにサイト所有者に回送されます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-199">When this is configured, site members' attempts to share files or folders by using *Specific people* links will go to the site owner for approval.</span></span>

<span data-ttu-id="c7f46-200">サイト、ファイル、およびフォルダーの共有を所有者に制限するには</span><span class="sxs-lookup"><span data-stu-id="c7f46-200">To limit site, file, and folder sharing to owners</span></span>
1. <span data-ttu-id="c7f46-201">サイトにある歯車アイコンをクリックして、**[サイトの権限]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-201">In the site, click the gear icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="c7f46-202">**[共有の設定]** の下側にある **[共有設定を変更します]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-202">Under **Sharing settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="c7f46-203">**[サイト所有者のみが、ファイル、フォルダー、サイトを共有できます]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7f46-203">Select **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="c7f46-204">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-204">Click **Save**.</span></span>

    ![所有者のみに設定された SharePoint サイトの共有アクセス許可設定のスクリーンショット](../media/sharepoint-site-only-site-owners-can-share.png)

## <a name="sharepoint-guest-sharing"></a><span data-ttu-id="c7f46-206">SharePoint ゲスト共有</span><span class="sxs-lookup"><span data-stu-id="c7f46-206">SharePoint guest sharing</span></span>

<span data-ttu-id="c7f46-207">SharePoint または OneDrive のファイルおよびフォルダーの組織外のユーザーとの共有を禁止する場合は、組織全体または個別サイトのゲスト共有をオフにします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-207">If you want to prevent sharing SharePoint or OneDrive files and folders with people outside your organization, you can turn off guest sharing for the entire organization or for an individual site.</span></span>

<span data-ttu-id="c7f46-208">組織の SharePoint ゲスト共有をオフにするには</span><span class="sxs-lookup"><span data-stu-id="c7f46-208">To turn off SharePoint guest sharing for your organization</span></span>
1. <span data-ttu-id="c7f46-209">SharePoint 管理センターで、**[ポリシー]** の下側にある **[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-209">In the SharePoint admin center, under **Policies**, click **Sharing**.</span></span>
2. <span data-ttu-id="c7f46-210">**[外部共有]** で、SharePoint のスライダーを **[自分の組織内のユーザーのみ]** に下げます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-210">Under **External sharing**, drag the SharePoint slider down to **Only people in your organization**.</span></span>
3. <span data-ttu-id="c7f46-211">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-211">Click **Save**.</span></span>

    ![Anyone に設定された SharePoint 組織レベルの共有設定のスクリーンショット](../media/sharepoint-tenant-sharing-off.png)


<span data-ttu-id="c7f46-213">サイトのゲスト共有をオフにするには</span><span class="sxs-lookup"><span data-stu-id="c7f46-213">To turn off guest sharing for a site</span></span>
1. <span data-ttu-id="c7f46-214">SharePoint 管理センターで、**[サイト]** の下側にある **[アクティブなサイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-214">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="c7f46-215">構成するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-215">Click the site that you want to configure.</span></span>
3. <span data-ttu-id="c7f46-216">**[ポリシー]** タブで、**[外部共有]** の下側にある **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-216">On the **Policies** tab, under **External sharing** click **Edit**.</span></span>
4. <span data-ttu-id="c7f46-217">**[外部共有]** で、**[組織内のユーザーのみ]** を選択して **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-217">Under **External sharing**, choose **Only people in your organization**, and then click **Save**.</span></span>

    ![[組織内のユーザーのみ] に設定された SharePoint のサイトレベルの共有設定のスクリーンショット](../media/sharepoint-site-external-sharing-settings-off.png)

<span data-ttu-id="c7f46-219">Microsoft 365 管理センターでユーザーをクリックし、**[OneDrive]** タブで **[外部共有を管理する]** を選択すると、個々の OneDrive のゲスト共有をオフにできます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-219">You can turn off guest sharing for an individual OneDrive by clicking the user in the Microsoft 365 admin center and selecting **Manage external sharing** on the **OneDrive** tab.</span></span>

<span data-ttu-id="c7f46-220">組織外のユーザーとの共有を許可するときに、すべてのユーザーが認証されているようにするには、組織全体または個別サイトの *すべてのユーザー* (匿名の共有) リンクを無効にします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-220">If you would like to allow sharing with people outside your organization but you want to make sure that everyone authenticates, you can disable *Anyone* (anonymous sharing) links for the entire organization or for an individual site.</span></span>

<span data-ttu-id="c7f46-221">組織レベルで *すべてのユーザー* リンクをオフにするには</span><span class="sxs-lookup"><span data-stu-id="c7f46-221">To turn off *Anyone* links at the organization level</span></span>
1. <span data-ttu-id="c7f46-222">SharePoint 管理センターで、**[ポリシー]** の下側にある **[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-222">In the SharePoint admin center, under **Policies**, click **Sharing**.</span></span>
2. <span data-ttu-id="c7f46-223">**[外部共有]** で、SharePoint のスライダーを **[新規および既存のゲスト]** に下げます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-223">Under **External sharing**, drag the SharePoint slider down to **New and existing guests**.</span></span>
3. <span data-ttu-id="c7f46-224">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-224">Click **Save**.</span></span>

    ![新規および既存のゲストに設定された SharePoint 組織レベルの共有設定のスクリーンショット](../media/sharepoint-guest-sharing-new-existing-guests.png)

<span data-ttu-id="c7f46-226">サイトの *すべてのユーザー* リンクをオフにするには</span><span class="sxs-lookup"><span data-stu-id="c7f46-226">To turn off *Anyone* links for a site</span></span>
1. <span data-ttu-id="c7f46-227">SharePoint 管理センターで、**[サイト]** の下側にある **[アクティブなサイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-227">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="c7f46-228">構成するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-228">Click the site that you want to configure.</span></span>
3. <span data-ttu-id="c7f46-229">**[ポリシー]** タブで、**[外部共有]** の下側にある **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-229">On the **Policies** tab, under **External sharing** click **Edit**.</span></span>
4. <span data-ttu-id="c7f46-230">**[外部共有]** で、**[新規および既存のゲスト]** を選択して **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f46-230">Under **External sharing**, choose **New and existing guests**, and then click **Save**.</span></span>

    ![新規および既存の設定に設定された SharePoint サイトレベルの共有設定のスクリーンショット](../media/sharepoint-site-external-sharing-settings-new-existing-guests.png)

## <a name="people-in-your-organization-sharing-links"></a><span data-ttu-id="c7f46-232">*組織内のユーザー* 共有リンク</span><span class="sxs-lookup"><span data-stu-id="c7f46-232">*People in your organization* sharing links</span></span>

<span data-ttu-id="c7f46-233">既定では、サイトのメンバーは組織外のユーザーとファイルおよびフォルダーを共有するために、*組織外のユーザー* リンクを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-233">By default, members of a site can share files and folders with other people in your organization by using a *People in your organization* link.</span></span> <span data-ttu-id="c7f46-234">*組織外のユーザー* リンクは、PowerShell を使用して無効化できます</span><span class="sxs-lookup"><span data-stu-id="c7f46-234">You can disable *People in your organization* links by using PowerShell:</span></span>

```powershell
Set-SPOSite -Identity <site> -DisableCompanyWideSharingLinks
```

<span data-ttu-id="c7f46-235">例:</span><span class="sxs-lookup"><span data-stu-id="c7f46-235">For example:</span></span>

```powershell
Set-SPOSite -Identity https://contoso.sharepoint.com -DisableCompanyWideSharingLinks
```

## <a name="create-sites-groups-and-teams"></a><span data-ttu-id="c7f46-236">サイト、グループ、チームを作成する</span><span class="sxs-lookup"><span data-stu-id="c7f46-236">Create sites, groups, and teams</span></span>

<span data-ttu-id="c7f46-237">既定では、ユーザーは新しいサイト、グループ、およびチームを作成して、そこからコンテンツを共有できるようにすることができます （共有設定によって異なります）。</span><span class="sxs-lookup"><span data-stu-id="c7f46-237">By default, users can create new sites, groups, and teams from which they may be able to share content (depending on your sharing settings).</span></span> <span data-ttu-id="c7f46-238">サイト、グループ、およびチームを作成できるユーザーを制限できます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-238">You can restrict who can create sites, groups, and teams.</span></span> <span data-ttu-id="c7f46-239">次の参考資料を参照してください:</span><span class="sxs-lookup"><span data-stu-id="c7f46-239">See the following references:</span></span>

- [<span data-ttu-id="c7f46-240">SharePoint のサイト作成を管理する</span><span class="sxs-lookup"><span data-stu-id="c7f46-240">Manage site creation in SharePoint</span></span>](/sharepoint/manage-site-creation)
- [<span data-ttu-id="c7f46-241">Microsoft 365 グループを作成できるユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="c7f46-241">Manage who can create Microsoft 365 Groups</span></span>](./manage-creation-of-groups.md)

> [!NOTE]
> <span data-ttu-id="c7f46-242">グループの作成を制限すると、チームの作成が制限されます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-242">Restricting group creation restricts team creation.</span></span>

## <a name="email"></a><span data-ttu-id="c7f46-243">メール</span><span class="sxs-lookup"><span data-stu-id="c7f46-243">Email</span></span>

<span data-ttu-id="c7f46-244">電子メールの不要な共有は、暗号化を使用することで防止できます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-244">You can prevent unwanted sharing of emails by using encryption.</span></span> <span data-ttu-id="c7f46-245">これにより、電子メールの転送や許可されていないユーザーとの共有を防止できます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-245">This prevents emails being forwarded or otherwise shared with unauthorized users.</span></span> <span data-ttu-id="c7f46-246">電子メールの暗号化は、秘密度ラベルを使用することで有効にできます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-246">Email encryption can be enabled by using sensitivity labels.</span></span> <span data-ttu-id="c7f46-247">詳細については、「[機密ラベルの暗号化を使用してコンテンツへのアクセスを制限する](../compliance/encryption-sensitivity-labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7f46-247">See [Restrict access to content by using encryption in sensitivity labels](../compliance/encryption-sensitivity-labels.md) for details.</span></span>

## <a name="download-or-file-copy"></a><span data-ttu-id="c7f46-248">ダウンロードまたはファイルのコピー</span><span class="sxs-lookup"><span data-stu-id="c7f46-248">Download or file copy</span></span>

<span data-ttu-id="c7f46-249">Microsoft 365 のファイルとフォルダーにアクセスできるユーザーは、ファイルをダウンロードして外部メディアにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="c7f46-249">Users who have access to files and folders in Microsoft 365 can download files and copy them to external media.</span></span> <span data-ttu-id="c7f46-250">不要なファイル共有のリスクを軽減するために、機密度ラベルを使用して内容を暗号化してください。</span><span class="sxs-lookup"><span data-stu-id="c7f46-250">To reduce the risk of unwanted file sharing, you can encrypt the content by using sensitivity labels.</span></span>

## <a name="conditional-access"></a><span data-ttu-id="c7f46-251">条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="c7f46-251">Conditional access</span></span>

<span data-ttu-id="c7f46-252">Azure Active Directory の条件付きアクセスは、ネットワークの場所、デバイスの正常性、サインイン リスク、およびその他の要因に基づいて、ユーザーとの共有を制限または防止するオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="c7f46-252">Azure Active Directory conditional access provides options to limit or prevent sharing with people based on network location, device health, sign-in risk, and other factors.</span></span> <span data-ttu-id="c7f46-253">「[条件付きアクセスとは?](/azure/active-directory/conditional-access/overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7f46-253">See [What is Conditional Access?](/azure/active-directory/conditional-access/overview).</span></span>

<span data-ttu-id="c7f46-p117">SharePoint は、非管理対象デバイスとネットワークの場所の両方に対して、Azure AD の条件付きアクセスとの直接統合を提供します。詳細については、次の参考資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7f46-p117">SharePoint provides direct integration with Azure AD conditional access for both unmanaged devices and network location. See the following references for details:</span></span>

- [<span data-ttu-id="c7f46-256">非管理対象デバイスからのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="c7f46-256">Control access from unmanaged devices</span></span>](/sharepoint/control-access-from-unmanaged-devices)
- [<span data-ttu-id="c7f46-257">ネットワークの場所に基づいて SharePoint と OneDrive のデータへのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="c7f46-257">Control access to SharePoint and OneDrive data based on network location</span></span>](/sharepoint/control-access-based-on-network-location)

## <a name="see-also"></a><span data-ttu-id="c7f46-258">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7f46-258">See also</span></span>

[<span data-ttu-id="c7f46-259">Microsoft 365 ゲストの共有設定のリファレンス</span><span class="sxs-lookup"><span data-stu-id="c7f46-259">Microsoft 365 guest sharing settings reference</span></span>](microsoft-365-guest-settings.md)